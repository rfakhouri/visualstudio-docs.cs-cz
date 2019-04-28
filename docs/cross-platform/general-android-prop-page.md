---
title: Obecné vlastnosti projektů (Android C++) | Dokumentace Microsoftu
ms.custom: ''
ms.date: 10/23/2017
ms.technology: vs-ide-mobile
ms.topic: conceptual
ms.assetid: 65f4868b-b864-4989-a275-1e51869ef599
author: corob
ms.author: mblome
manager: jillfra
f1_keywords:
- VC.Project.VCConfiguration.OutputDirectory
- VC.Project.VCConfiguration.IntermediateDirectory
- VC.Project.VCConfiguration.TargetName
- VC.Project.VCConfiguration.TargetExt
- VC.Project.VCConfiguration.DeleteExtensionsOnClean
- VC.Project.VCConfiguration.BuildLogFile
- VC.Project.VCConfiguration.PlatformToolset
- VC.Project.VCConfiguration.ConfigurationType
- VC.Project.VCConfiguration.DeleteExtensionsOnClean
- VC.Project.VCConfiguration.UseOfSTL
- VC.Project.VCConfiguration.ThumbMode
ms.workload:
- xplat-cplusplus
ms.openlocfilehash: 4bb6f26fe40b639b43cb803577a785fa9b48823d
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62818944"
---
# <a name="general-project-properties-android-c"></a>Obecné vlastnosti projektů (Android C++)

Vlastnost | Popis | Možnosti
--- | ---| ---
Výstupní adresář | Určuje relativní cestu k adresáři výstupního souboru; může obsahovat proměnné prostředí.
Zprostředkující adresář | Určuje relativní cestu k adresáři přechodového souboru; může obsahovat proměnné prostředí.
Cílový název | Určuje název souboru, který bude tento projekt generovat.
Cílová přípona | Určuje rozšíření souboru, který bude tento projekt generovat. (Příklad: *.exe* nebo *.dll*)
Přípony odstraňované při čištění | Středníkem oddělená specifikace zástupných znaků určujících, které soubory v přechodovém adresáři odstranit při čištění nebo opětovném sestavení.
Soubor protokolu sestavení | Určuje soubor protokolu sestavení pro zápis při protokolování sestavení je povolená.
Sada nástrojů platformy | Určuje, nástrojů pro sestavení aktuální konfigurace. Pokud není využito set, výchozí sady nástrojů
Typ konfigurace | Určuje typ výstupu generovaného touto konfigurací. | **Dynamická knihovna (.so)** – dynamická knihovna (*.so*)<br>**Statická knihovna (.a)** – statická knihovna (*.a*)<br>**Nástroj** – nástroj<br>**Soubor pravidel** -souboru pravidel<br>
Cílová úroveň rozhraní API | Android NDK rozhraní API: úroveň kterou míří tato konfigurace.
Použití STL | Určuje, která standardní knihovna C++ použít pro tuto konfiguraci. | **Minimální knihovny prostředí runtime jazyka C++ (systém)**<br>**C++prostředí stlport (gabi ++ _static)**<br>**C++sdílená knihovna běhového (gabi ++ _shared)**<br>**Sdílená knihovna běhového prostředí stlport (stlport_static)**<br>**Sdílená knihovna běhového prostředí (stlport stlport_shared)**<br>**Statická knihovna GNU STL (gnustl_static)**<br>**Sdílená knihovna GNU STL (gnustl_shared)**<br>**Knihovna LLVM libc ++ statické (c ++ _static)**<br>**Knihovna LLVM libc ++ sdílené (c ++ _shared)**<br>
Režim thumb | Generovat kód, který spouští pro mikroarchitekturu thumb. To platí jenom pro architekturu arm. | **Miniatury**<br>**Arm**<br>**Disabled** (Zakázáno)<br>
