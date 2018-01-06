---
title: "Visual Studio Tools for Unity Azure návod | Microsoft Docs"
ms.custom: 
ms.date: 10/19/2017
ms.reviewer: crdun
ms.suite: 
ms.technology: tgt-pltfrm-cross-plat
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7921D4C7-5526-42F5-8E03-82D3E33A893F
author: dantogno
ms.author: v-davian
manager: crdun
ms.workload:
- azure
- unity
ms.openlocfilehash: d5242dd873591abee15f528d09b6f588ea12f5ba
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="using-azure-easy-tables-with-unity-walkthrough"></a>Pomocí tabulky Azure snadno návod Unity

![Ukázka herní – snímek obrazovky](media/vstu_azure-test-sample-game-image2.png)

## <a name="introduction"></a>Úvod

Azure poskytuje škálovatelné řešení k ukládání telemetrie a dalších herní dat v cloudu. S vydáním Unity 2017 Unity na podporu pro rozhraní .NET 4.6 díky integrace se službou Azure jednodušší než někdy tím, že se používat Azure Mobile klienta SDK.

Tyto kroky provede procesem nastavení Unity projekt, který využívá pro ukládání telemetrie a žebříček dat v cloudu Azure.

> [!NOTE]
> Tento projekt vyžaduje "experimentální" runtime .NET 4.6 Mono skriptování v Unity 2017. [Unity má uvádí, že brzy to bude výchozí](https://forum.unity3d.com/threads/future-plans-for-the-mono-runtime-upgrade.464327/), ale zatím stále označen jako "experimentální" a může dojít k problémům.

> Tento názorný postup dokumentů. Příklad pro připojení k back-end mobilní aplikace Azure ze sestavení Unity PC. V době psaní tohoto dokumentu jsou známé problémy, které blokovat tento projekt fungovat na platformách Mac a Android. Toto jsou známé problémy, které bude opraven, i když neví časovou osu. Další informace najdete v článku Unity [experimentální skriptování fórum](https://forum.unity3d.com/forums/experimental-scripting-previews.107/).

## <a name="download-the-completed-project"></a>Stáhněte si dokončený projekt

Dokončený projekt je dostupná na Githubu. Průvodce však bude předpokládat, jsou od projektu prázdné, nové a poskytne odkazy na stažení prostředky, pokud je to nezbytné.

## <a name="walkthrough-steps"></a>Kroky názorného postupu

1. [Konfigurace jednoduchých tabulek v Azure](visual-studio-tools-for-unity-azure-configure.md)
2. [Vytvoření jednoduchých tabulek](visual-studio-tools-for-unity-azure-setup.md)
3. [Příprava vývojového prostředí](visual-studio-tools-for-unity-azure-prepare.md)
4. [Vytvoření tříd datových modelů](visual-studio-tools-for-unity-azure-data.md)
5. [Implementace třídy MobileServiceClient v Azure](visual-studio-tools-for-unity-azure-mobile-client.md)
6. [Aktualizace úložiště certifikátů zabezpečení Unity Mono](visual-studio-tools-for-unity-azure-security.md)
7. [Testování připojení klienta](visual-studio-tools-for-unity-azure-connection.md)
7. [Import ukázkových herních prostředků](visual-studio-tools-for-unity-azure-game-assets.md)
8. [Testování ukázky hry](visual-studio-tools-for-unity-azure-game.md)
9. [Vysvětlení k RaceScene](visual-studio-tools-for-unity-azure-racescene.md)
10. [Vysvětlení k HeatmapScene](visual-studio-tools-for-unity-azure-heatmapscene.md)
11. [Vysvětlení k LeaderboardScene](visual-studio-tools-for-unity-azure-leaderboardscene.md)


## <a name="next-step"></a>Další krok
* [Konfigurace jednoduchých tabulek v Azure](visual-studio-tools-for-unity-azure-configure.md)
