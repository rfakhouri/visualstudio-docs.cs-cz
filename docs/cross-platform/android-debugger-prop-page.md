---
title: "Vlastnosti Android ladicího programu (C++) | Microsoft Docs"
ms.custom: 
ms.date: 10/23/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-mobile
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 789f7a1c-38b4-41d0-809b-14f4d96c8116
author: corob
ms.author: mblome
manager: ghogen
f1_keywords:
- VC.Project.AndroidDebugger.DebuggerType
- VC.Project.AndroidDebugger.AndroidDeviceID
- VC.Project.AndroidDebugger.PackagePath
- VC.Project.AndroidDebugger.LaunchActivity
ms.workload:
- xplat-cplusplus
ms.openlocfilehash: 3ca25e560a4bc3060d86972b4000b3d9ad59ba1f
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/09/2018
---
# <a name="android-debugger-properties"></a>Vlastnosti Android ladicí program

Vlastnost | Popis | Možnosti
--- | ---| ---
Typ ladicí program | Určuje typ kódu k ladění. | **Jenom Native**<br>**Pouze Java**<br>
Ladění cíl | Určuje emulátoru nebo zařízení, které chcete použít pro ladění. Pokud se žádné emulátorů běží, použijte 'Manager virtuální zařízení Android (AVD)' při spuštění zařízení.
Balíček pro spuštění | Určuje umístění .apk, který bude ladit. Tuto volbu použijte k určení, že konkrétní balíček (APK) by měl být spuštěn, když je ladit aplikace.
Spuštění aktivity | Android aktivity sloužící ke spuštění aplikace, musí odpovídat používaný v manifestu. Klepněte na tlačítko použít k načtení seznamu z AndroidManifest.xml a přidejte do ní dynamicky.
Cesty hledání další Symbol | Další vyhledávací cesta pro symboly ladění.
Cesty hledání zdroj další Java | Cesty hledání další pro jazyk Java zdrojové soubory. (Platí, pouze pokud ladicí program je typ Java pouze malá a velká písmena.)
