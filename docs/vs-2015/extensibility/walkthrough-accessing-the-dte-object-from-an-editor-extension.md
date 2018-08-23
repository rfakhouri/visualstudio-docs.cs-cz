---
title: 'Návod: Přístup k objektu DTE z rozšíření editoru | Dokumentace Microsoftu'
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
- editors [Visual Studio SDK], new - getting the DTE object
ms.assetid: c1f40bab-c6ec-45b0-8333-ea5ceb02a39d
caps.latest.revision: 23
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 91d1683b6c2743df2f04d6462ae0a57ec7b0aff4
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42674201"
---
# <a name="walkthrough-accessing-the-dte-object-from-an-editor-extension"></a>Návod: Přístup k objektu DTE z rozšíření editoru
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [návod: přístup k objektu DTE z rozšíření editoru](https://docs.microsoft.com/visualstudio/extensibility/walkthrough-accessing-the-dte-object-from-an-editor-extension).  
  
V balíčcích VSPackage, můžete získat objekt DTE zavoláním <xref:Microsoft.VisualStudio.Shell.Package.GetService%2A> metoda s typem objektu DTE. V rozšíření Managed Extensibility Framework (MEF), můžete importovat <xref:Microsoft.VisualStudio.Shell.SVsServiceProvider> a následně zavolat <xref:Microsoft.VisualStudio.Shell.ServiceProvider.GetService%2A> metoda s typem <xref:EnvDTE.DTE>.  
  
## <a name="prerequisites"></a>Požadavky  
 Chcete-li postupovat podle tohoto návodu, je nutné nainstalovat sadu Visual Studio SDK. Další informace najdete v tématu [Visual Studio SDK](../extensibility/visual-studio-sdk.md).  
  
## <a name="getting-the-dte-object"></a>Získání objektu DTE  
  
#### <a name="to-get-the-dte-object-from-the-serviceprovider"></a>Chcete-li získat objekt DTE z poskytovatel služeb  
  
1.  Vytvořte projekt VSIX C# s názvem `DTETest`. Přidejte šablony položky editoru třídění a pojmenujte ho `DTETest`. Další informace najdete v tématu [vytváření rozšíření pomocí šablony položky editoru](../extensibility/creating-an-extension-with-an-editor-item-template.md).  
  
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
  
4.  V `GetDTEProvider` třídy, importovat <xref:Microsoft.VisualStudio.Shell.SVsServiceProvider>.  
  
    ```csharp  
    [Import]  
    internal SVsServiceProvider ServiceProvider = null;  
  
    ```  
  
5.  V `GetClassifier()` metodu, přidejte následující kód.  
  
    ```csharp  
    DTE dte = (DTE)ServiceProvider.GetService(typeof(DTE));  
  
    ```  
  
6.  Pokud je nutné použít <xref:EnvDTE80.DTE2> rozhraní, můžete přetypovat objekt DTE k němu.  
  
## <a name="see-also"></a>Viz také  
 [Rozšiřovací body služeb jazyka a editoru](../extensibility/language-service-and-editor-extension-points.md)

