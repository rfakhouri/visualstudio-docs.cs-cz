---
title: "Příkazy a nabídky, které používají sestavení vzájemné spolupráce | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- menus, using interop assemblies
- interop assemblies, using in commands and menus
- commands, handling using interop assemblies
- command handling with interop assemblies
ms.assetid: 8f4af525-39e5-4e69-92c8-d3efabe80bb2
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 8d89b698a97d1793b3c5255966d9eca35ec1b78f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="commands-and-menus-that-use-interop-assemblies"></a>Příkazy a nabídky, které používají spolupráce – sestavení
Musí být VSPackage, který implementuje příkazy nabídek a panelů nástrojů pomocí spolupráce – sestavení:  
  
-   Informujte [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] integrované vývojové prostředí (IDE) o příkazech podporuje a zda jsou nyní zapnuta.  
  
-   Splňovat pravidla pro zpracování příkazů (kontrakt).  
  
-   Explicitní implementace zpracování příkazu pomocí <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> nebo <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy> rozhraní.  
  
 Následující text popisuje, jak to provést tyto úlohy.  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Určení stavu příkazu pomocí spolupracujícího sestavení](../../extensibility/internals/determining-command-status-by-using-interop-assemblies.md)  
 Popisuje, jak VSPackage upozorní IDE o které příkazy podporuje, a zda jsou nyní zapnuta.  
  
 [Kontrakty příkazů ve spolupracujícím sestavení](../../extensibility/internals/command-contracts-in-interop-assemblies.md)  
 Poskytuje definici kontraktu základní příkaz používané všechny VSPackages implementace příkazů pomocí spolupráce – sestavení  
  
 [Implementace](../../extensibility/internals/command-implementation.md)  
 Poskytuje přehled o tom, jak VSPackage implementuje příkaz.  
  
 [Registrace obslužných rutin příkazů spolupracujícího sestavení](../../extensibility/internals/registering-interop-assembly-command-handlers.md)  
 Popisuje položky registru IDE oznámit, že poskytuje VSPackage obslužná rutina příkazu.  
  
## <a name="related-sections"></a>Související oddíly  
 [Dostupnost](../../extensibility/internals/command-availability.md)  
 Popisuje kritéria, která se používají zařízení IDE k určení, které VSPackage příkazy jsou k dispozici a jaké objekt zpracovává je.  
  
 [Jak balíčky VSPackages přidávají prvky uživatelského rozhraní](../../extensibility/internals/how-vspackages-add-user-interface-elements.md)  
 Poskytuje podrobné informace o tom, jak vytvářet uživatelské rozhraní, která používá [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] příkaz podpory.  
  
 [Směrování příkazů v balíčcích VSPackage](../../extensibility/internals/command-routing-in-vspackages.md)  
 Přehled procesu používá k propojení objekt s správný příkaz žádosti.