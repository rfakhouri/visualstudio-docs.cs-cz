---
title: "Optimalizace nabídky a příkazy nástrojů | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- commands [Visual Studio], menus
- commands [Visual Studio], toolbars
- menus [Visual Studio SDK], commands
- menu commands, implementing
- toolbars [Visual Studio], commands
ms.assetid: 8385f1a6-1e98-4dca-83d2-fcbed7177242
caps.latest.revision: "8"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: f95675f420284b9d67a6d36ac30b3e71f085e565
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="optimizing-menu-and-toolbar-commands"></a>Optimalizace nabídek a příkazů panelu nástrojů
Přidání VSPackages a jejich odpovídající příkazů [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] může způsobit frekventované uživatelského rozhraní. [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]poskytuje způsoby, jak zachování přehlednosti příkaz uživatelského rozhraní.  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Zpřístupnění příkazů](../../extensibility/internals/making-commands-available.md)  
 Obsahuje obecné pokyny pro minimalizaci nakupením [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] uživatelského rozhraní při přidání VSPackages.  
  
 [Pokyny pro umístění](../../extensibility/internals/command-placement-guidelines.md)  
 Poskytuje konkrétní pokyny pro implementaci VSPackage na základě velikosti sadu příkazů.  
  
## <a name="related-sections"></a>Související oddíly  
 [Příkazy, nabídky a panely nástrojů](../../extensibility/internals/commands-menus-and-toolbars.md)  
 Vysvětluje, jak vytvářet uživatelské rozhraní, které obsahuje nabídky, panely nástrojů a příkaz pole se seznamem.