---
title: "Visual Studio Tools for Unity Azure návod HeatmapScene | Microsoft Docs"
ms.custom: 
ms.date: 10/19/2017
ms.reviewer: crdun
ms.suite: 
ms.technology: tgt-pltfrm-cross-plat
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: E11DA08B-7341-4743-A817-0CAD59844305
author: dantogno
ms.author: v-davian
manager: crdun
ms.openlocfilehash: f707052e0ec0b9cda60c111767800c1ce14d6103
ms.sourcegitcommit: ee42a8771f0248db93fd2e017a22e2506e0f9404
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/09/2017
---
# <a name="heatmapscene-explanation"></a>Vysvětlení HeatmapScene

HeatmapScene obsahuje instanci **LevelGeometry** prefab. Tímto způsobem souřadnice pro havárií načetla z Azure mapování správně na úrovni obrázky.

## <a name="heatmap-script"></a>Heatmap skriptu

### <a name="initializecrashlistasync"></a>InitializeCrashListAsync
`InitializeCrashListAsync`připojí k tabulce snadno CrashInfo v Azure a používá <a href="https://msdn.microsoft.com/en-us/library/azure/jj554274(v=azure.10).aspx"> `ToListAsync` </a> přidat všechny jeho položky do seznamu.

```
private async Task InitializeCrashListAsync()
 {
     Debug.Log("Downloading crash data from Azure...");

     for (int i = 0; i < numberOfAttempts; i++)
     {
         try
         {
             Debug.Log("Connecting... attempt " + (i +1));
             crashesFromServer = await crashesTable.ToListAsync();
             Debug.Log("Done downloading.");
             return;
         }
         catch (System.Exception e)
         {
             Debug.Log("Error connecting: " + e.Message);
         }

         if (i == numberOfAttempts - 1)
             Debug.Log("Connection failed. Check logs, try again later.");
         else
             await Task.Delay(500);
     }
 }
```

### <a name="spawnmarkersfromlist"></a>SpawnMarkersFromList
`SpawnMarkersFromList`prochází seznam havárií přijaté z Azure a vytvoří prefab značky havárií pro každou položku.

```csharp
private void SpawnMarkersFromList()
{
    foreach (var item in crashesFromServer)
    {
        GameObject marker = GameObject.Instantiate(markerPrefab);
        marker.transform.position = new Vector3 { x = item.X, y = item.Y, z = item.Z };
    }
}
```

### <a name="deletecrashdataasync"></a>DeleteCrashDataAsync

`DeleteCrashDataAsync`je volána, když uživatel stiskne **vymazat Data** tlačítko. Iteruje v rámci místního seznamu dojde k chybě a volání <a href="https://msdn.microsoft.com/en-us/library/azure/jj554258(v=azure.10).aspx"> `DeleteAsync` </a> pro každou položku. Toto nastaví každou položku **odstraněné** sloupec v tabulce snadno **true**. `ToListAsync`ignoruje tyto odstraněné položky.

```csharp
public async void DeleteCrashDataAsync()
{
    Debug.Log("Deleting crash data...");
    foreach (var item in crashesFromServer)
    {
        try
        {
            await crashesTable.DeleteAsync(item);
        }
        catch (System.Exception e)
        {
            Debug.Log("Error deleting crash data: " + e.Message);
        }
        Debug.Log("Done deleting crash data.");
    }
    SceneManager.LoadScene(SceneManager.GetActiveScene().name);
}
```

## <a name="next-step"></a>Další krok

* [Vysvětlení LeaderboardScene](visual-studio-tools-for-unity-azure-leaderboardscene.md)