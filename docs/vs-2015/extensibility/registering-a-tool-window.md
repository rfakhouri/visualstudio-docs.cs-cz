---
title: Registrace panelu nástrojů | Dokumentace Microsoftu
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tool windows, registering managed
- tool windows, registering
ms.assetid: 8c8c4a24-3da4-497b-9db2-0ddd7cfbfdd2
caps.latest.revision: 15
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 14dc8020247214ef812a93cb4518e5dfeeb502d1
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/12/2018
ms.locfileid: "49213574"
---
# <a name="registering-a-tool-window"></a>Registrace panelu nástrojů
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Můžete zaregistrovat pomocí nástroje windows <xref:Microsoft.VisualStudio.Shell.ProvideToolWindowAttribute> a  <xref:Microsoft.VisualStudio.Shell.ProvideToolWindowVisibilityAttribute>  
  
## <a name="example"></a>Příklad  
  
```csharp  
  
      [ProvideToolWindow(typeof(PersistedWindowPane), Style = MsVsShell.VsDockStyle.Tabbed, Window = "3ae79031-e1bc-11d0-8f78-00a0c9110057")] [ProvideToolWindow(typeof(DynamicWindowPane), PositionX=250, PositionY=250, Width=160, Height=180, Transient=true)] [ProvideToolWindowVisibility(typeof(DynamicWindowPane), /*UICONTEXT_SolutionExists*/"f1536ef8-92ec-443c-9ed7-fdadf150da82")]  
[ProvideMenuResource(1000, 1)]  
[PackageRegistration(UseManagedResourcesOnly = true)]  
[Guid("01069CDD-95CE-4620-AC21-DDFF6C57F012")]  
public class PackageToolWindow : Package  
{  
```  
  
 Ve výše uvedeném kódu <xref:Microsoft.VisualStudio.Shell.ProvideToolWindowAttribute> zaregistruje PersistedWindowPane a DynamicWindowPane okna nástrojů pomocí sady Visual Studio. Panel nástrojů trvalý je ukotvena a s kartami s **Průzkumníka řešení**, a dynamické okno bude mít výchozí počáteční pozice a velikost. Dynamické okno se provádí přechodné, což znamená, že není vytvořeno při spuštění. To zapíše hodnotu DontForceCreate ToolWindows klíče v registru systému. Další informace najdete v tématu [konfigurace zobrazení okna nástroje](../extensibility/tool-window-display-configuration.md).

