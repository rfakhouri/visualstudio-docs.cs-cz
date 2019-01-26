---
title: Obecné vlastnosti projektů (Android C++ Makefile) | Dokumentace Microsoftu
ms.custom: ''
ms.date: 10/23/2017
ms.technology: vs-ide-mobile
ms.topic: conceptual
ms.assetid: f76d717c-56ed-4373-8cf9-9bd1a053a4cd
author: corob
ms.author: mblome
manager: jillfra
f1_keywords:
- VC.Project.VCConfiguration.OutputDirectory
- VC.Project.VCConfiguration.IntermediateDirectory
- VC.Project.VCConfiguration.BuildLogFile
- VC.Project.VCConfiguration.ConfigurationType
ms.workload:
- xplat-cplusplus
ms.openlocfilehash: ee398add6b0cca8288d82cd090e1abef07a40d23
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55041760"
---
# <a name="general-project-properties-android-c-makefile"></a>Obecné vlastnosti projektu (Android C++ Makefile)

Vlastnost | Popis | Možnosti
--- | ---| ---
Výstupní adresář | Určuje relativní cestu k adresáři výstupního souboru; může obsahovat proměnné prostředí.
Zprostředkující adresář | Určuje relativní cestu k adresáři přechodového souboru; může obsahovat proměnné prostředí.
Soubor protokolu sestavení | Určuje soubor protokolu sestavení pro zápis při protokolování sestavení je povolená.
Typ konfigurace | Určuje typ výstupu generovaného touto konfigurací. | **Dynamická knihovna (.so)** – dynamická knihovna (*.so*)<br>**Statická knihovna (.a)** – statická knihovna (*.a*)<br>**Nástroj** – nástroj<br>**Soubor pravidel** -souboru pravidel<br>
