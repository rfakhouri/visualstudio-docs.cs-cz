---
title: "Obecné vlastnosti projektu (Android C++) | Microsoft Docs"
ms.custom: 
ms.date: 10/23/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 65f4868b-b864-4989-a275-1e51869ef599
author: corob
ms.author: mblome
manager: ghogen
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
ms.workload: xplat-cplusplus
ms.openlocfilehash: e18fffbe0eb3104ec445fca7d791d74f5bf02bf9
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="general-project-properties-android-c"></a>Obecné vlastnosti projektu (Android C++)

Vlastnost | Popis | Možnosti
--- | ---| ---
Výstupní adresář | Určuje relativní cestu do výstupního adresáře. soubor; může obsahovat proměnné prostředí.
Zprostředkující adresáře | Určuje relativní cestu k adresáři pomocný soubor; může obsahovat proměnné prostředí.
Cílový název | Určuje název souboru, který bude generovat tento projekt.
Přípona cílového | Určuje příponu souboru, která bude vytvářet tento projekt. (Příklad: .exe nebo .dll)
Rozšíření k odstranění na vyčištění | Oddělte středníkem oddělené specifikace zástupný znak, pro které soubory v adresáři zprostředkující odstranit na čištění nebo znovu vytvořit.
Vytvoření souboru protokolu | Určuje soubor protokolu sestavení pro zápis, když sestavení protokolování je povolena.
Sada nástrojů platformy | Určuje sada nástrojů používá pro vytváření aktuální konfiguraci; Není-li se používá sada, výchozí sady nástrojů
Typ konfigurace | Určuje typ výstupu, který generuje tuto konfiguraci. | **Dynamické knihovny (.so)** -dynamické knihovny (.so)<br>**Statické knihovny (.a)** – statické knihovny (.a)<br>**Nástroj** – nástroj<br>**Makefile** -souboru pravidel<br>
Úroveň cílové rozhraní API | Android NDK API úrovně cílem této konfigurace.
Použití STL | Určuje, které standardní knihovna C++ pro tuto konfiguraci. | **Minimální běhové knihovny jazyka c (systém)**<br>**Statické knihovny C++ runtime (gabi ++ _statickou)**<br>**Sdílené knihovny C++ runtime (gabi ++ _sdíleno)**<br>**Statické knihovny STLport runtime (stlport_static)**<br>**STLport runtime sdílené knihovny (stlport_shared)**<br>**Statické knihovny GNU STL (gnustl_static)**<br>**Sdílené knihovny GNU STL (gnustl_shared)**<br>**LLVM libc ++ statické knihovny (c ++ _statickou)**<br>**LLVM libc ++ sdílené knihovny (c ++ _sdíleno)**<br>
Jezdec režimu | Generování kódu, které provádí pro mikroarchitektura jezdce. To platí pro pouze pro architekturu arm. | **Jezdec**<br>**Arm**<br>**Zakázané**<br>
