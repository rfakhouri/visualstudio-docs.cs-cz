---
title: "Visual Studio Tools for Unity Azure návod připojení | Microsoft Docs"
ms.custom: 
ms.date: 10/19/2017
ms.reviewer: crdun
ms.suite: 
ms.technology: tgt-pltfrm-cross-plat
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 516A8FB2-8DFF-4BAB-8116-FDCD1C228DB3
author: dantogno
ms.author: v-davian
manager: crdun
ms.openlocfilehash: f21e320fe9e27f6873b9caed3048a93bfa94a9c4
ms.sourcegitcommit: ee42a8771f0248db93fd2e017a22e2506e0f9404
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/09/2017
---
# <a name="test-the-client-connection"></a>Testovací připojení klienta

Je teď vytvořená AzureMobileServiceClient singleton, je čas k testování připojení klienta.

## <a name="create-the-testclientconnection-script"></a>Vytvořit skript TestClientConnection

1. Uvnitř **skripty** složky v Unity, vytvořte nový skript jazyka C# s názvem **TestClientConnection**.

2. Otevřete skript v sadě Visual Studio, odstranit všechny kód šablony a přidat následující:

  ```csharp
  using System.Collections.Generic;
  using UnityEngine;
  using System.Threading.Tasks;
  using System;
  using System.Linq;
  using Microsoft.WindowsAzure.MobileServices;

  public class TestClientConnection : MonoBehaviour
  {
      void Start()
      {
          Task.Run(TestTableConnection);
      }

      private async Task TestTableConnection()
      {
          var table = AzureMobileServiceClient.Client.GetTable<CrashInfo>();

          Debug.Log("Testing ToListAsync...");
          await TestToListAsync(table);

          Debug.Log("Testing InsertAsync...");
          await TestInsertAsync(table);

          Debug.Log("Testing DeleteAsync...");
          await TestDeleteAsync(table);

          Debug.Log("All testing complete.");
      }

      private async Task TestInsertAsync(IMobileServiceTable<CrashInfo> table)
      {
          try
          {
              var allEntries = await TestToListAsync(table);
              var initialCount = allEntries.Count();

              await table.InsertAsync(new CrashInfo { X = 1, Y = 2, Z = 3 });

              allEntries = await TestToListAsync(table);
              var newCount = allEntries.Count();

              Debug.Assert(newCount == initialCount + 1, "InsertAsync failed!");
          }
          catch (Exception)
          {
              throw;
          }
      }

      private async Task<List<CrashInfo>> TestToListAsync(IMobileServiceTable<CrashInfo> table)
      {
          try
          {
              var allEntries = await table.ToListAsync();
              Debug.Assert(allEntries != null, "ToListAsync failed!");
              return allEntries;
          }
          catch (Exception)
          {

              throw;
          }
      }

      private async Task TestDeleteAsync(IMobileServiceTable<CrashInfo> table)
      {
          var allEntries = await TestToListAsync(table);

          foreach (var item in allEntries)
          {
              try
              {
                  await table.DeleteAsync(item);
              }
              catch (Exception)
              {
                  throw;
              }
          }

          allEntries = await TestToListAsync(table);

          Debug.Assert(allEntries.Count() == 0, "DeleteAsync failed!");
      }
  }
  ```

3. V Unity **GameObject** nabídce vyberte možnost **GameObject > vytvořit prázdnou** vytvořit prázdný GameObject v scény Unity. Přejmenujte ji **TestClientConnection**.

4. **Přetáhněte** TestClientConnection skript z Unity **projektu** okna do TestClientConnection GameObject v **hierarchie** okno.

5. V nabídce Unity vyberte **soubor > scény uložit jako...** . Název scény **Test připojení klienta** a klikněte na tlačítko **Uložit**.

5. Klikněte **přehrání** tlačítka na Unity a podívejte se v okně konzoly. Potvrďte, žádný z kontrolní výrazy se nezdařilo.

6. Otevřete CrashInfo snadno tabulky na portálu Azure. Nyní měli položku s **X, Y, Z** souřadnic **(1, 2, 3)** a hodnota **true** pro v **odstranit** sloupce. Při každém spuštění testu, nové položky se stejné hodnoty, ale jedinečné ID musí být přidaní do tabulky.

  ![Snadno záznam tabulky](media/vstu_azure-test-client-connection-image1.png)

## <a name="next-step"></a>Další krok
* [Import herní prostředky ukázka](visual-studio-tools-for-unity-azure-game-assets.md).
