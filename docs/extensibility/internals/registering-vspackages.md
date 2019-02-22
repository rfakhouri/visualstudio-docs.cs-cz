---
title: Registrace balíčků VSPackage | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- managed VSPackages, registering
- registration, managed VSPackages
ms.assetid: 79b9424e-7e9b-4fc8-9b9f-00212674573c
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 426adc0cd150d5867760a8570df5777fec8260a2
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56601574"
---
# <a name="registering-vspackages"></a>Registrace balíčků VSPackage
[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] závisí na souborech .pkgdef k popisu a vyhledejte VSPackage. Soubor .pkgdef obsahuje všechny informace o registraci, které by jinak přidán do systémového registru. Spravovaná rozšíření VSPackages zaregistrováni přidávání atributů do zdrojového kódu a následným spuštěním [nástroj CreatePkgDef](../../extensibility/internals/createpkgdef-utility.md) výsledné sestavení se vygenerovat soubor .pkgdef.

## <a name="in-this-section"></a>V tomto oddílu
- [Specifikace umístění souboru balíčku VSPackage pro prostředí sady VS](../../extensibility/internals/specifying-vspackage-file-location-to-the-vs-shell.md)

 Popisuje cestu načítání rozšíření VSPackages.

- [Registrace a zrušení registrace rozšíření VSPackages](../../extensibility/registering-and-unregistering-vspackages.md)

 Vysvětluje, jak zaregistrovat VSPackage.
