---
title: Nasazení projektu typy | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- projects [Visual Studio SDK], managed-code
- projects [Visual Studio SDK], aggregator
ms.assetid: 7f132f67-8589-464c-90dc-0d57ae02aa8f
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 12af8607dd1561a4a2561cc688d2bb4ba0f07c88
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31127971"
---
# <a name="deploying-project-types"></a>Nasazení typy projektů
[!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)] nainstaluje nový agregátor typu projektu (ProjectAggregator2.dll) a také balíček Instalační služby systému Windows pro opětovnou distribuci (ProjectAggregator2.msi). Je nutné použít nový agregátor pro typy projektů spravovaného kódu. ProjectAggregator2 funguje postupy omezení [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] projektu agregátoru, které zabrání typy projektů spravovaného kódu z funguje správně. Následující kroky popisují, jak chcete-li změnit váš VSPackage používat se novému agregátoru.  
  
1.  Projekt NativeHierarchyWrapper odeberte z vašeho řešení.  
  
2.  Odeberte všechny binární soubory NativeHierarchyWrapper z vašeho nastavení.  
  
3.  Přidejte ProjectAggregator2.msi do vašeho nastavení.