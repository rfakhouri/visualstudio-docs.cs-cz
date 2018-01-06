---
title: "Visual Studio Tools for Unity prostředky Azure herní návod | Microsoft Docs"
ms.custom: 
ms.date: 10/19/2017
ms.reviewer: crdun
ms.suite: 
ms.technology: tgt-pltfrm-cross-plat
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: C06FAB2E-F592-4EFF-B96A-58858C92DCEB
author: dantogno
ms.author: v-davian
manager: crdun
ms.workload:
- azure
- unity
ms.openlocfilehash: 19b98dc472b9e01529725b95133d289edff6334d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="import-sample-game-assets"></a>Import ukázkových herní prostředky

Teď, když byl otestován a pracovat předvedená základní funkce, je čas k importu herní ukázkové prostředky.

## <a name="import-package"></a>Import balíčku

1. Stažení [ukázkové prostředky herní balíček](https://github.com/dantogno/UnityAzureSample/blob/master/Azure%20Easy%20tables%20sample%20game%20assets.unitypackage).

2. Zkontrolujte, zda že je otevřený projekt Unity potom přejděte do umístění pro stahování a dvakrát klikněte na soubor. Tím se otevře dialogové okno importu ve Unity.

3. Klikněte na tlačítko **všechny** a pak klikněte na **Import**. Počkejte, než pro výsledný indikátory průběhu k dokončení.

  ![Import balíčku](media/vstu_azure-import-sample-assets-image1.png)

## <a name="add-scenes-to-build-settings"></a>Přidání scény do nastavení sestavení

Jakmile soubory dokončili, import, je nutné přidat soubory požadované scény v nastavení sestavení projektu Unity.

1. V okně Unity projektu, přejděte na **snadno tabulky Azure ukázkové herní prostředky nebo scény** adresáře.

2. V nabídce Unity vyberte **soubor > Vytvořit nastavení...** . Zobrazí se dialogové okno nastavení sestavení.

3. Přetáhněte **HeatmapScene**, **LeaderboardScene**, **MenuScene**, a **RaceScene** soubory z okna projekt do **Scény v sestavení** části dialogového okna nastavení sestavení.

  ![Import balíčku](media/vstu_azure-import-sample-assets-image2.png)

4. V nabídce Unity vyberte **soubor > Uložit projektu** zajistit nastavení sestavení se ukládají.

## <a name="next-step"></a>Další krok

* [Testování ukázky hry](visual-studio-tools-for-unity-azure-game.md)