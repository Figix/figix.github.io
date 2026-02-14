---
title: "Unity SceneUI View Toggle"
description: 
date: 2026-02-14T09:39:06+09:00
image: 
math: 
license: 
comments: true
draft: false
categories:
    - Tools
tags:
    - Unity
build:
    list: always    # Change to "never" to hide the page from the list
---
Unity에서 Unreal처럼 SceneView의 보이는 UI에 대한 Toggle키를 만들었습니다.  

[SceneViewGameModeToggle.zip 다운로드](SceneViewGameModeToggle.zip)

```cs
#if UNITY_EDITOR

using UnityEditor;
using UnityEngine;

[InitializeOnLoad]
public static class SceneViewGameModeToggle
{
    static bool isGameMode = false;

    static SceneViewGameModeToggle()
    {
        SceneView.duringSceneGui += OnSceneGUI;
    }

    static void OnSceneGUI(SceneView sceneView)
    {
        Event e = Event.current;

        if (e.type == EventType.KeyDown && e.keyCode == KeyCode.G)
        {
            ToggleGameMode(sceneView);
            e.Use(); // 이벤트 소비
        }
    }

    static void ToggleGameMode(SceneView sceneView)
    {
        isGameMode = !isGameMode;

        // Gizmo on/off
        sceneView.drawGizmos = !isGameMode;

        // Selection outline / wireframe
        Tools.hidden = isGameMode;

        // Scene 아이콘 (라이트, 카메라 등)
        AnnotationUtility.SetIconState(isGameMode ? 0 : 1);

        SceneView.RepaintAll();
    }
}

/// <summary>
/// 내부 API (아이콘 표시 제어)
/// </summary>
static class AnnotationUtility
{
    static System.Type annotationUtilityType;
    static System.Reflection.MethodInfo setIconEnabledMethod;

    static AnnotationUtility()
    {
        annotationUtilityType = typeof(Editor).Assembly.GetType("UnityEditor.AnnotationUtility");
        setIconEnabledMethod = annotationUtilityType.GetMethod(
            "SetIconEnabled",
            System.Reflection.BindingFlags.Static | System.Reflection.BindingFlags.NonPublic
        );
    }

    public static void SetIconState(int enabled)
    {
        var annotations = annotationUtilityType.GetMethod(
            "GetAnnotations",
            System.Reflection.BindingFlags.Static | System.Reflection.BindingFlags.NonPublic
        ).Invoke(null, null) as System.Array;

        foreach (var annotation in annotations)
        {
            var classId = (int)annotation.GetType().GetField("classID").GetValue(annotation);
            var scriptClass = (string)annotation.GetType().GetField("scriptClass").GetValue(annotation);
            setIconEnabledMethod.Invoke(null, new object[] { classId, scriptClass, enabled });
        }
    }
}

#endif
```