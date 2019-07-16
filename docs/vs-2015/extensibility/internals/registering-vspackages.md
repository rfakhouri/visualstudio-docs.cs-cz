---
title: Registrace balíčků VSPackage | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- managed VSPackages, registering
- registration, managed VSPackages
ms.assetid: 79b9424e-7e9b-4fc8-9b9f-00212674573c
caps.latest.revision: 21
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 053157b0ce1cb4250d8c666725431515c75b5fa2
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68157393"
---
# <a name="registering-vspackages"></a>Registrace balíčků VSPackage
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] závisí na souborech .pkgdef k popisu a vyhledejte VSPackage. Soubor .pkgdef obsahuje všechny informace o registraci, které by jinak přidán do systémového registru. Spravovaná rozšíření VSPackages zaregistrováni přidávání atributů do zdrojového kódu a následným spuštěním [nástroj CreatePkgDef](../../extensibility/internals/createpkgdef-utility.md) výsledné sestavení se vygenerovat soubor .pkgdef.  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Specifikace umístění souboru balíčku VSPackage pro prostředí sady VS](../../extensibility/internals/specifying-vspackage-file-location-to-the-vs-shell.md)  
 Popisuje cestu načítání rozšíření VSPackages.  
  
 [Registrace a zrušení registrace rozšíření VSPackages](../../extensibility/registering-and-unregistering-vspackages.md)  
 Vysvětluje, jak zaregistrovat VSPackage.  
  
 [Pomocí atributu vlastní registrace k registraci rozšíření](../../misc/using-a-custom-registration-attribute-to-register-an-extension.md)  
 Popisuje postup vytvoření registrace manifestu, který slouží k nasazení spravované VSPackage.
