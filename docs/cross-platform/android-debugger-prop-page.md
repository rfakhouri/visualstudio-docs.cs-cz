---
title: Vlastnosti ladicího programu pro Android (C++) | Dokumentace Microsoftu
ms.custom: ''
ms.date: 10/23/2017
ms.technology: vs-ide-mobile
ms.topic: conceptual
ms.assetid: 789f7a1c-38b4-41d0-809b-14f4d96c8116
author: corob
ms.author: mblome
manager: jillfra
f1_keywords:
- VC.Project.AndroidDebugger.DebuggerType
- VC.Project.AndroidDebugger.AndroidDeviceID
- VC.Project.AndroidDebugger.PackagePath
- VC.Project.AndroidDebugger.LaunchActivity
ms.workload:
- xplat-cplusplus
ms.openlocfilehash: 9a4d7baa970008c2de7a3bc28966f7edbad68b21
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62819500"
---
# <a name="android-debugger-properties"></a>Vlastnosti ladicího programu pro Android

Vlastnost | Popis | Možnosti
--- | ---| ---
Typ ladicího programu | Určuje, který typ kódu k ladění. | **Pouze nativní**<br>**Jenom Java**<br>
Cíl ladění | Určuje emulátor nebo zařízení pro ladění. Pokud žádné emulátory neběží, použijte "Android Virtual Device (AVD) Manager" zařízení spusťte.
Balíček ke spuštění | Určuje umístění *.apk* , který bude laděn. Tato možnost slouží k určení, že konkrétní balíček APK má být spuštěn při ladění aplikace.
Spouštěcí aktivita | Aktivita v Androidu použít ke spuštění aplikace, musí odpovídat tomu použitému v manifestu. Klepněte na tlačítko použít k získání seznamu z *AndroidManifest.xml* a dynamicky ho naplníte.
Další cesty hledání symbolů | Další cesty hledání pro symboly ladění.
Cesty hledání zdrojového další Java | Další cesty hledání pro zdrojové soubory Javy. (Platí, pouze když je typ ladicího programu jenom Java.)
