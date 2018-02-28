---
title: "Návod: Přístup k objektu DTE z rozšíření editoru | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- editors [Visual Studio SDK], new - getting the DTE object
ms.assetid: c1f40bab-c6ec-45b0-8333-ea5ceb02a39d
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: af14fa5f9a76e08a1fba3355e9391ce8229bd652
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-accessing-the-dte-object-from-an-editor-extension"></a>Návod: Přístup k objektu DTE z rozšíření editoru
V VSPackages, můžete získat objekt DTE voláním <xref:Microsoft.VisualStudio.Shell.Package.GetService%2A> metoda s typem DTE objektu. V rozšíření Managed Extensibility Framework (MEF), můžete importovat <xref:Microsoft.VisualStudio.Shell.SVsServiceProvider> a pak zavolají <xref:Microsoft.VisualStudio.Shell.ServiceProvider.GetService%2A> metoda s typem <xref:EnvDTE.DTE>.  
  
## <a name="prerequisites"></a>Požadavky  
 Chcete-li provést tento postup, je nutné nainstalovat sadu Visual Studio SDK. Další informace najdete v tématu [Visual Studio SDK](../extensibility/visual-studio-sdk.md).  
  
## <a name="getting-the-dte-object"></a>Získávání DTE objektu  
  
#### <a name="to-get-the-dte-object-from-the-serviceprovider"></a>Chcete-li získat objekt DTE z poskytovatel služeb  
  
1.  Vytvoření projektu C# VSIX s názvem `DTETest`. Přidání šablony položky Editor třídění a pojmenujte ji `DTETest`. Další informace najdete v tématu [vytváření rozšíření pomocí šablony položky Editor](../extensibility/creating-an-extension-with-an-editor-item-template.md).  
  
2.  Přidejte následující odkazy na sestavení do projektu:  
  
    -   EnvDTE  
  
    -   EnvDTE80  
  
    -   Microsoft.VisualStudio.Shell.Immutable.10.0  
  
3.  Přejděte k souboru DTETest.cs a přidejte následující `using` direktivy:  
  
    ```csharp  
    using EnvDTE;  
    using EnvDTE80;  
    using Microsoft.VisualStudio.Shell;  
  
    ```  
  
4.  V `GetDTEProvider` třídy, naimportujte <xref:Microsoft.VisualStudio.Shell.SVsServiceProvider>.  
  
    ```csharp  
    [Import]  
    internal SVsServiceProvider ServiceProvider = null;  
  
    ```  
  
5.  V `GetClassifier()` metoda, přidejte následující kód.  
  
    ```csharp  
    DTE dte = (DTE)ServiceProvider.GetService(typeof(DTE));  
  
    ```  
  
6.  Pokud budete muset použít <xref:EnvDTE80.DTE2> rozhraní, můžete převést objekt DTE k němu.  
  
## <a name="see-also"></a>Viz také  
 [Rozšiřovací body služeb jazyka a editoru](../extensibility/language-service-and-editor-extension-points.md)