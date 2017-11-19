---
title: "Visual Studio Tools for Unity Azure návod RaceScene | Microsoft Docs"
ms.custom: 
ms.date: 10/19/2017
ms.reviewer: crdun
ms.suite: 
ms.technology: tgt-pltfrm-cross-plat
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1F9304E8-0F1B-4325-8BED-FE3EB0ADCE8D
author: dantogno
ms.author: v-davian
manager: crdun
ms.openlocfilehash: 304fb69ab6e5da058cd3d2a4d6de202fa042b8f9
ms.sourcegitcommit: ee42a8771f0248db93fd2e017a22e2506e0f9404
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/09/2017
---
# <a name="racescene-explanation"></a>Vysvětlení RaceScene

RaceScene používá Unity [standardní prostředky](https://www.assetstore.unity3d.com/en/#!/content/32351) k vytvoření základní dostihy hraní her a úroveň. V této části relevantní GameObjects a jejich skripty budou vysvětleny v pořadí, ve kterém jsou uvedeny v RaceScene zásobník, jak je uvedeno v následující snímek obrazovky.

![RaceScene](media/vstu_azure-racescene-explanation-image1.png)

## <a name="multipurposecamerarig"></a>MultipurposeCameraRig

**MultipurposeCameraRig** z **kamery** balíček standardní prostředky. Jeho vlastnosti Inspector byla naladit přijímání postupujte podle Car na odpovídající rychlosti.

## <a name="levelgeometry"></a>LevelGeometry

LevelGeometry prefab je prázdný GameObject používají k uspořádání. Jeho podřízené GameObjects tvoří možné přehrát místa. Podlah, stěn, rampy a překážek jsou všechny vybudována prefabs v **při vytváření prototypu** balíček standardní prostředky.

**Důležité OneNote** je, že v pořadí pro objekt, který má být testována pro havárií, ke kterým se zaznamenávají v Azure, musí mít **Wall** značky použít.

![RaceScene](media/vstu_azure-racescene-explanation-image2.png)

## <a name="car"></a>Auto

**Car** prefab je z **vozidel** balíček standardní prostředky. Pouze úpravy je, že **RecordCrashInfo** přidání komponenty skriptu.

### <a name="recordcrashinfo"></a>RecordCrashInfo

Tento skript kontroluje dojde k chybě v `OnCollisionEnter` a zaznamenává je do seznamu. `crashRecordingCooldown`a `crashRecordingMinVelocity` omezit, co hra považuje za havárie abychom zachovali příslušné datové sady.

Když `RaceFinished` událost se vyvolá, `UploadNewCrashDataAsync` odešle každý havárie v seznamu snadno tabulky CrashInfo v Azure.

```Csharp
using System.Collections;
using System.Collections.Generic;
using System.Threading.Tasks;
using UnityEngine;

public class RecordCrashInfo : MonoBehaviour
{
    [Tooltip("Time in seconds after a crash before a new crash can be recorded.")]
    [SerializeField]
    private float crashRecordingCooldown = 1;

    [Tooltip("How fast car must be traveling before crash can be recorded.")]
    [SerializeField]
    private float crashRecordingMinVelocity = 8;

    [SerializeField]
    private Rigidbody carRigidbody;

    [SerializeField]
    private GameObject crashMarkerPrefab;

    [Tooltip("If turned on, crash markers spawn when the player crashes.")]
    [SerializeField]
    private bool spawnDebugMarkers = false;

    private bool isOnCooldown = false;
    private bool meetsMinVelocity = false;
    private bool isRaceFinished = false;

    private List<CrashInfo> newCrashes = new List<CrashInfo>();

    private void LateUpdate()
    {
        // We have to update this in LateUpdate as opposed to checking in OnCollisionEnter.
        // The car's velocity has already decreased from crashing by the time
        // OnCollisionEnter gets called.

        meetsMinVelocity = carRigidbody.velocity.magnitude >= crashRecordingMinVelocity;
    }

    private void OnCollisionEnter(Collision collision)
    {
        if (!isRaceFinished && collision.gameObject.tag == "Wall" && !isOnCooldown && meetsMinVelocity)
        {
            Debug.Log("Collided with wall!");

            newCrashes.Add(new CrashInfo
            {
                X = collision.transform.position.x,
                Y = collision.transform.position.y,
                Z = collision.transform.position.z
            });

            if (spawnDebugMarkers && Debug.isDebugBuild)
                Instantiate(crashMarkerPrefab, collision.transform.position, Quaternion.identity);

            isOnCooldown = true;
            StartCoroutine(Cooldown());
        }  
    }

    private IEnumerator Cooldown()
    {
        yield return new WaitForSeconds(crashRecordingCooldown);

        isOnCooldown = false;
    }

    private void OnRaceFinished()
    {
        Task.Run(UploadNewCrashDataAsync);
    }

    private async Task UploadNewCrashDataAsync()
    {
        var crashTable = AzureMobileServiceClient.Client.GetTable<CrashInfo>();

        try
        {
            Debug.Log("Uploading crash data to Azure...");

            foreach (var item in newCrashes)
            {
                await crashTable.InsertAsync(item);
            }
            Debug.Log("Finished uploading crash data.");
        }
        catch (System.Exception e)
        {
            Debug.Log("Error uploading crash data: " + e.Message);
        }

    }

    private void OnEnable()
    {
        Checkpoint.RaceFinished += OnRaceFinished;
    }

    private void OnDisable()
    {
        Checkpoint.RaceFinished -= OnRaceFinished;
    }

}
```

## <a name="checkpoints"></a>Kontrolní body

Úroveň má čtyři GameObjects s **kontrolního bodu** součást skriptu. Kontrolní body zkontrolujte, zda že hráč nejde dokončit soupeření podle cestě nesprávný směrem dolů sledování. Zjistí také po dokončení soupeření přehrávač. To je, kdy `RaceFinished` událost vyvolána.

## <a name="invisible-collision"></a>Neviditelná kolizí

Standardní primitivní datové krychle s jejich MeshRenderer součásti zakázáno slouží jako neviditelné kolizí zachovat inbounds přehrávač. Kromě toho **Bouncy** fyziky materiálu platí zajistit pohybujících vrátit odesílateli aut vypnout neviditelná bariéry vyhovuje požadavkům způsobem a aby player z stiskne neviditelná wall, klouzavé dolů ho a cílová stránka nad viditelné Wall.

## <a name="recordhighscore"></a>RecordHighScore

Tento skript zkontroluje, pokud má přehrávač vytvořené nové vysoké skóre. Pokud budou mít, zobrazí se `enterNamePopup`, což umožňuje player zadejte jeho název a klikněte na tlačítko **odeslání**.

Po odeslání název player `UploadNewHighScoreAsync` nazývá a nové vysoké skóre jsou odeslána do tabulky snadno HighScoreInfo v Azure.

```csharp
using System.Collections;
using System.Collections.Generic;
using Microsoft.WindowsAzure.MobileServices;
using UnityEngine;
using System.Threading.Tasks;
using System;
using System.Linq;
using UnityEngine.UI;

public class RecordHighScore : MonoBehaviour
{
    [SerializeField]
    private InputField nameInputField;

    [SerializeField]
    private CanvasGroup enterNamePopup;

    private List<HighScoreInfo> highScores;
    private string playerName = string.Empty;

    private async void Start()
    {
        ShowEnterNamePopup(false);
        highScores = await Leaderboard.GetTopHighScoresAsync();
    }

    private void ShowEnterNamePopup(bool shouldShow)
    {
        enterNamePopup.alpha = shouldShow ? 1 : 0;
        enterNamePopup.interactable = shouldShow;
    }

    public void SubmitButtonClicked()
    {
        playerName = nameInputField.text;
    }

    private async void OnAfterMostRecentScoreSet(float newScore)
    {
        bool isNewHighScore = CheckForNewHighScore(newScore);

        if (isNewHighScore)
        {
            Debug.Log("New High Score!");
            await GetPlayerNameAsync();
            await UploadNewHighScoreAsync(newScore);
        }
        else
        {
            Debug.Log("No new high score.");
        }
    }

    private async Task GetPlayerNameAsync()
    {
        // Wait a bit before showing the popup.
        // This just helps the player experience feel
        // less jarring.
        await Task.Delay(2000);
        ShowEnterNamePopup(true);

        // Wait until the player enters a name and clicks submit.
        // OnSubmitButtonClicked will set the playerName.
        while (playerName == string.Empty)
        {
            await Task.Delay(100);
        }

        ShowEnterNamePopup(false);
    }

    private bool CheckForNewHighScore(float newScore)
    {
        Debug.Log("Checking for a new high score...");

        bool isHighScoreListFull = highScores.Count >= Leaderboard.SizeOfHighScoreList;
        var lowerScores = highScores.Where(x => x.Time > newScore);

        return lowerScores.Count() > 0 || !isHighScoreListFull;
    }

    private async Task UploadNewHighScoreAsync(float newScore)
    {
        var newHighScoreInfo = new HighScoreInfo { Name = playerName, Time = newScore };

        try
        {
            Debug.Log("Uploading high score data to Azure...");

            await Leaderboard.HighScoreTable.InsertAsync(newHighScoreInfo);

            Debug.Log("Finished uploading high score data.");
        }
        catch (System.Exception e)
        {
            Debug.Log("Error uploading high score data: " + e.Message);
        }
    }

    private void OnEnable()
    {
        LapTimer.AfterMostRecentScoreSet += OnAfterMostRecentScoreSet;
    }

    private void OnDisable()
    {
        LapTimer.AfterMostRecentScoreSet -= OnAfterMostRecentScoreSet;
    }

}
```

## <a name="next-step"></a>Další krok

* [Vysvětlení HeatmapScene](visual-studio-tools-for-unity-azure-heatmapscene.md).
