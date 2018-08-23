---
title: Nasazování typů projektů | Dokumentace Microsoftu
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
- projects [Visual Studio SDK], managed-code
- projects [Visual Studio SDK], aggregator
ms.assetid: 7f132f67-8589-464c-90dc-0d57ae02aa8f
caps.latest.revision: 13
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 66069ac71fbe59e8b63126d66d2a0cc63ed095bc
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42666584"
---
# <a name="deploying-project-types"></a>Nasazování typů projektů
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [nasazování typů projektů](https://docs.microsoft.com/visualstudio/extensibility/internals/deploying-project-types).  
  
[!INCLUDE[vsipsdk](../../includes/vsipsdk-md.md)] nainstaluje nový agregátor typu projektu (ProjectAggregator2.dll) a také balíček Instalační služby systému Windows pro automatické distribuce signatur (ProjectAggregator2.msi). Je nutné použít nový agregátor pro typy projektů spravovaného kódu. ProjectAggregator2 funguje postupy omezení [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] projektu agregátorem, který zabrání typy projektů spravovaný kód podle vašich představ. Následující kroky popisují, jak změnit vašeho balíčku VSPackage pro použití se novému agregátoru.  
  
1.  Odeberte projekt NativeHierarchyWrapper z vašeho řešení.  
  
2.  Odebrání binárních souborů NativeHierarchyWrapper vašeho nastavení.  
  
3.  Přidání ProjectAggregator2.msi do vašeho nastavení.

