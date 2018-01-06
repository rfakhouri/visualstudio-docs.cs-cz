---
title: "Registrace okno nástroje | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- tool windows, registering managed
- tool windows, registering
ms.assetid: 8c8c4a24-3da4-497b-9db2-0ddd7cfbfdd2
caps.latest.revision: "14"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 908a850b1e86ffc2e8337096266849efeaf04a51
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="registering-a-tool-window"></a>Registrace okno nástroje
Můžete zaregistrovat váš nástroj windows pomocí <xref:Microsoft.VisualStudio.Shell.ProvideToolWindowAttribute> a<xref:Microsoft.VisualStudio.Shell.ProvideToolWindowVisibilityAttribute>  
  
## <a name="example"></a>Příklad  
  
```csharp  
  
      [ProvideToolWindow(typeof(PersistedWindowPane), Style = MsVsShell.VsDockStyle.Tabbed, Window = "3ae79031-e1bc-11d0-8f78-00a0c9110057")] [ProvideToolWindow(typeof(DynamicWindowPane), PositionX=250, PositionY=250, Width=160, Height=180, Transient=true)] [ProvideToolWindowVisibility(typeof(DynamicWindowPane), /*UICONTEXT_SolutionExists*/"f1536ef8-92ec-443c-9ed7-fdadf150da82")]  
[ProvideMenuResource(1000, 1)]  
[PackageRegistration(UseManagedResourcesOnly = true)]  
[Guid("01069CDD-95CE-4620-AC21-DDFF6C57F012")]  
public class PackageToolWindow : Package  
{  
```  
  
 Ve výše, kódu <xref:Microsoft.VisualStudio.Shell.ProvideToolWindowAttribute> zaregistruje nástroj windows PersistedWindowPane a DynamicWindowPane pomocí sady Visual Studio. Okno trvalou nástroje je ukotvena a na kartách s **Průzkumníku**, a dynamické okno bude mít výchozí počáteční pozice a velikosti. Okno dynamické přišla přechodný, což naznačuje, že nebyl vytvořen při spuštění. To umožňuje zápis hodnoty DontForceCreate ToolWindows klíče v registru systému. Další informace najdete v tématu [konfigurace zobrazení okna nástroj](../extensibility/tool-window-display-configuration.md).