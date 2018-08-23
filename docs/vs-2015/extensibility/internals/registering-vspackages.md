---
title: Registrace balíčků VSPackage | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managed VSPackages, registering
- registration, managed VSPackages
ms.assetid: 79b9424e-7e9b-4fc8-9b9f-00212674573c
caps.latest.revision: 21
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 1c826b61e4f6d2255be7b7fdad967bab0d8dea74
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42665934"
---
# <a name="registering-vspackages"></a>Registrace balíčků VSPackage
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [registrace rozšíření VSPackages](https://docs.microsoft.com/visualstudio/extensibility/internals/registering-vspackages).  
  
[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] závisí na souborech .pkgdef k popisu a vyhledejte VSPackage. Soubor .pkgdef obsahuje všechny informace o registraci, které by jinak přidán do systémového registru. Spravovaná rozšíření VSPackages zaregistrováni přidávání atributů do zdrojového kódu a následným spuštěním [nástroj CreatePkgDef](../../extensibility/internals/createpkgdef-utility.md) výsledné sestavení se vygenerovat soubor .pkgdef.  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Specifikace umístění souboru balíčku VSPackage pro prostředí sady VS](../../extensibility/internals/specifying-vspackage-file-location-to-the-vs-shell.md)  
 Popisuje cestu načítání rozšíření VSPackages.  
  
 [Registrace a zrušení registrace rozšíření VSPackages](../../extensibility/registering-and-unregistering-vspackages.md)  
 Vysvětluje, jak zaregistrovat VSPackage.  
  
 [Pomocí atributu vlastní registrace k registraci rozšíření](../../misc/using-a-custom-registration-attribute-to-register-an-extension.md)  
 Popisuje postup vytvoření registrace manifestu, který slouží k nasazení spravované VSPackage.

