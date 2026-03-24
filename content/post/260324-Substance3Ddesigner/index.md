---
title: "Substance 3D Designer Blend Node"
date: 2026-03-24T19:50:06+09:00
license: MIt
comments: true
draft: false
categories:
    - Substance 3D Designer
tags:
    - 2026
build:
    list: always    # Change to "never" to hide the page from the list
---

https://experienceleague.adobe.com/en/docs/substance-3d-designer/using/substance-graphs/nodes-reference-for-substance-graphs/atomic-nodes/blend/blending-modes-description

위 링크는 서브스턴스 디자이너의 Blending Mode에 대해서 설명하는 Document 링크입니다.

Copy, Add (Linear dodge), Subtract, Multiply, Add sub, Max (Lighten), Min (Darken), Switch, Divide, Overlay, Screen, Soft light

총 12개의 블렌딩 모드가 있습니다.

## Substance Designer Blending Mode
```jsx
B = Background (Base)
F = Foreground (Blend)
Result = R
```

### Copy
그냥 위 레이어를 덮어쓴다. 알파값이 있으면 그걸로 섞는다.
```jsx
R = lerp(B, F, F_alpha)
```

### Add (Linear Dodge)
픽셀 값을 더한다 → 밝아짐
```jsx
R = saturate(B + F)
```

### Subtract
Foreground 값을 빼버림
```jsx
R = B - F
R = max(B - F, 0)
```

### Multiply
곱하기→항상 어두워짐
```jsx
R = B * F
```

### Add Sub
F 기준으로 분기
- F > 0.5 → Add
- F < 0.5 → Subtract
```jsx
if (F > 0.5):
    R = B + (F - 0.5) * 2
else:
    R = B - (0.5 - F) * 2
```

### Max (Lighten)
더 밝은 값 선택
```jsx
R = max(B, F)
```

### Min (Darken)
더 어두운 값 선택
```jsx
R = min(B, F)
```

### Switch
Copy와 비슷하지만, 연산 자체를 끊어버림
```jsx
if (Opacity == 0):
    R = B   (F 계산 안함)
else:
    R = F   (B 계산 안함)
```

### Divide
나눗셈 → 밝아짐 (F가 작으면 → 엄청 밝아짐)
```jsx
R = B / F
R = B / max(F, epsilon)
```

### Screen
Invert → Multiply → Invert (Multiply의 반대, 자연스러운 밝기 증가)
```jsx
R = 1 - (1 - B) * (1 - F)
```

### Overlay
Base 기준으로 분기하며, 대비 증가용으로 많이 사용함.
- B < 0.5 → Multiply
- B > 0.5 → Screen
```jsx
if (B < 0.5):
    R = 2 * B * F
else:
    R = 1 - 2 * (1 - B) * (1 - F)
```

### Soft Light
부드러운 Overlay 느낌, 대비가 부드럽게 증가함
- F > 0.5 → 밝게
- F < 0.5 → 어둡게
```jsx
R = (1 - 2F) * B^2 + 2F * B
```

### 정리
1. 대부분의 블렌드는 Multiply, Add, Lerp의 조합이다.
2. 0.5 기준 분기 = “중립값” → Overlay/SoftLight/AddSub

---
https://en.wikipedia.org/wiki/Blend_modes - 포토샵의 블렌딩 모드를 정리한 자료

수식에서 a는 아랫레이어, b는 윗레이어이므로; 즉 a는 Foreground, b는 Background이다.

## PhotoShap Blending Mode

### Normal (Copy)
```jsx
float blend_normal(float a, float b) {
    return b;
}
```

### Multiply
```jsx
float blend_multiply(float a, float b) {
    return a * b;
}
```

### Screen
```jsx
float blend_screen(float a, float b) {
    return 1.0 - (1.0 - a) * (1.0 - b);
}
//f(a,b) = 1 - (1-a)(1-b)
```

### Overlay
```jsx
float blend_overlay(float a, float b) {
    if (a < 0.5)
        return 2.0 * a * b;
    else
        return 1.0 - 2.0 * (1.0 - a) * (1.0 - b);
}
```

### Hard Light
```jsx
float blend_hardlight(float a, float b) {
    if (b < 0.5)
        return 2.0 * a * b + a * a * (1.0 - 2.0 * b);
    else
        return 2.0 * a * (1.0 - b) + sqrt(a) * (2.0 * b - 1.0);
}

// Overlay의 입력 뒤집은 버전입니다.
```

### Add (Linear Dodge)
```jsx
float blend_add(float a, float b) {
    return saturate(a + b);
}
```

### Subtract
```jsx
float blend_subtract(float a, float b) {
    return max(a - b, 0.0);
}
```

### Divide
```jsx
float blend_divide(float a, float b) {
    float epsilon = 1e-5;
    return saturate(a / max(b, epsilon));
}
// b가 작으면 폭발적으로 밝아짐
```

### Darken / Lighten
```jsx
float blend_darken(float a, float b) {
    return min(a, b);
}

float blend_lighten(float a, float b) {
    return max(a, b);
}

```

### Color Dodge
```jsx
float blend_color_dodge(float a, float b) {
    float epsilon = 1e-5;
    return saturate(a / (1.0 - b + epsilon));
}
// 밝은 영역을 강하게 밀어올림
```

### Color Burn
```jsx
float blend_color_burn(float a, float b) {
    float epsilon = 1e-5;
    return 1.0 - saturate((1.0 - a) / max(b, epsilon));
}
```

### Linear Burn
```jsx
float blend_linear_burn(float a, float b) {
    return saturate(a + b - 1.0);
}
```

### Linear Light
```jsx
float blend_linear_light(float a, float b) {
    return saturate(a + 2.0 * b - 1.0);
}
// Linear Dodge + Linear Burn 결합
```

### Difference
```jsx
float blend_difference(float a, float b) {
    return abs(a - b);
}
```

### Exclusion
```jsx
float blend_exclusion(float a, float b) {
    return a + b - 2.0 * a * b;
}
```

### Soft Light
```jsx
float blend_softlight(float a, float b) {
    if (b < 0.5)
        return 2.0 * a * b + a * a * (1.0 - 2.0 * b);
    else
        return sqrt(a) * (2.0 * b - 1.0) + 2.0 * a * (1.0 - b);
}
```

추가적으로 다른 모드들이 있고, 각종 모드들에 대해 정리한 글이 아래 링크에 있습니다.

https://figix.tistory.com/25