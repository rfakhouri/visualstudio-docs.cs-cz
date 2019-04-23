---
title: Nasazování typů projektů | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- projects [Visual Studio SDK], managed-code
- projects [Visual Studio SDK], aggregator
ms.assetid: 7f132f67-8589-464c-90dc-0d57ae02aa8f
caps.latest.revision: 13
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 0fda84d5f7467a65b254d3b12b0466b6ab415d61
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60076469"
---
# <a name="deploying-project-types"></a>Nasazování typů projektů
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

[!INCLUDE[vsipsdk](../../includes/vsipsdk-md.md)] nainstaluje nový agregátor typu projektu (ProjectAggregator2.dll) a také balíček Instalační služby systému Windows pro automatické distribuce signatur (ProjectAggregator2.msi). Je nutné použít nový agregátor pro typy projektů spravovaného kódu. ProjectAggregator2 funguje postupy omezení [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] projektu agregátorem, který zabrání typy projektů spravovaný kód podle vašich představ. Následující kroky popisují, jak změnit vašeho balíčku VSPackage pro použití se novému agregátoru.  
  
1. Odeberte projekt NativeHierarchyWrapper z vašeho řešení.  
  
2. Odebrání binárních souborů NativeHierarchyWrapper vašeho nastavení.  
  
3. Přidání ProjectAggregator2.msi do vašeho nastavení.
