---
title: Registrace VSPackages | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managed VSPackages, registering
- registration, managed VSPackages
ms.assetid: 79b9424e-7e9b-4fc8-9b9f-00212674573c
caps.latest.revision: "20"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 2d580d3d74d8648b7181ac1ca384d3232fa8225b
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="registering-vspackages"></a>Registrace VSPackages
[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]spoléhá na soubory .pkgdef popsat a vyhledejte VSPackage. Soubor .pkgdef obsahuje všechny informace o registraci, které by jinak bylo možné přidat do registru systému. Spravované VSPackages jsou registrované přidáním atributy ke zdrojovému kódu a pak spustit [CreatePkgDef nástroj](../../extensibility/internals/createpkgdef-utility.md) na výsledné sestavení můžete vytvořit soubor .pkgdef.  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Zadání umístění souboru VSPackage prostředí VS](../../extensibility/internals/specifying-vspackage-file-location-to-the-vs-shell.md)  
 Popisuje cestu načítání pro VSPackages.  
  
 [Registrace a zrušení registrace VSPackages](../../extensibility/registering-and-unregistering-vspackages.md)  
 Vysvětluje, jak zaregistrovat VSPackage.  
