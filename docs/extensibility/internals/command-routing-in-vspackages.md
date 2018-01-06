---
title: "Příkaz směrování v VSPackages | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- commands, routing
- command routing, Visual Studio SDK
ms.assetid: a9c7f9ae-3594-4557-a314-8cf76f5f8772
caps.latest.revision: "24"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 90f3d2347f8bf37173f3eb257293b71d706eb0a0
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="command-routing-in-vspackages"></a>Směrování příkazů v VSPackages
Příkaz se směruje v [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] na základě kontextu, ve kterém se spustí. Z pasivního počáteční kontextu je směrována na globálním kontextu.  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Směrování algoritmus](../../extensibility/internals/command-routing-algorithm.md)  
 Popisuje pořadí příkaz směrování řešení.  
  
 [Dostupnost](../../extensibility/internals/command-availability.md)  
 Popisuje směrování příkazů.  
  
 [Příkazy a nabídky, které používají spolupracující sestavení](../../extensibility/internals/commands-and-menus-that-use-interop-assemblies.md)  
 Popisuje aspekty příkazy směrování mezi spravovaného kódu a COM.  
  
## <a name="related-sections"></a>Související oddíly  
 [Kontextové objekty výběru](../../extensibility/internals/selection-context-objects.md)  
 Popisuje model pro určení uživatele výběr kontextu se zaměřují na okno.  
  
 [Příkazy, nabídky a panely nástrojů](../../extensibility/internals/commands-menus-and-toolbars.md)  
 Vysvětluje, jak vytvářet uživatelské rozhraní, které obsahuje nabídky, panely nástrojů a příkaz pole se seznamem.