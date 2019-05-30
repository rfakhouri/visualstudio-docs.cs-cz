---
title: Přístup k objektu DTE z rozšíření editoru
ms.date: 04/24/2019
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], new - getting the DTE object
ms.assetid: c1f40bab-c6ec-45b0-8333-ea5ceb02a39d
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 1fb22793c3bfa805fae11c8bbea7f07c06fd5a85
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66322791"
---
# <a name="walkthrough-access-the-dte-object-from-an-editor-extension"></a>Návod: Přístup k objektu DTE z rozšíření editoru

V balíčcích VSPackage, můžete získat objekt DTE zavoláním <xref:Microsoft.VisualStudio.Shell.Package.GetService%2A> metoda s typem objektu DTE. V rozšíření Managed Extensibility Framework (MEF), můžete importovat <xref:Microsoft.VisualStudio.Shell.SVsServiceProvider> a následně zavolat <xref:Microsoft.VisualStudio.Shell.ServiceProvider.GetService%2A> metoda s typem <xref:EnvDTE.DTE>.

## <a name="prerequisites"></a>Požadavky

Chcete-li postupovat podle tohoto návodu, je nutné nainstalovat sadu Visual Studio SDK. Další informace najdete v tématu [Visual Studio SDK](../extensibility/visual-studio-sdk.md).

## <a name="get-the-dte-object"></a>Získat objekt DTE

1. Vytvoření C# VSIX projekt a pojmenujte ho **DTETest**. Přidat **Editor třídění** šablony položky a pojmenujte ho **DTETest**.

   Další informace najdete v tématu [vytváření rozšíření pomocí šablony položky editoru](../extensibility/creating-an-extension-with-an-editor-item-template.md).

::: moniker range=">=vs-2019"

2. Přidejte následující odkaz na sestavení do projektu:

    - Microsoft.VisualStudio.Shell.Immutable.10.0

3. V *DTETestProvider.cs* soubor, přidejte následující `using` direktivy:

    ```csharp
    using EnvDTE;
    using Microsoft.VisualStudio.Shell;
    ```

4. V `DTETestProvider` třídy, import <xref:Microsoft.VisualStudio.Shell.SVsServiceProvider>.

    ```csharp
    [Import]
    internal SVsServiceProvider ServiceProvider = null;
    ```

5. V `GetClassifier()` metodu, přidejte následující kód před `return` – příkaz:

    ```csharp
   ThreadHelper.ThrowIfNotOnUIThread();
   DTE dte = (DTE)ServiceProvider.GetService(typeof(DTE));
   ```

::: moniker-end

::: moniker range="vs-2017"

2. Přidejte následující odkazy na sestavení do projektu:

   - EnvDTE
   - Microsoft.VisualStudio.Shell.Framework

3. V *DTETestProvider.cs* soubor, přidejte následující `using` direktivy:

    ```csharp
    using EnvDTE;
    using Microsoft.VisualStudio.Shell;
    ```

4. V `DTETestProvider` třídy, import <xref:Microsoft.VisualStudio.Shell.SVsServiceProvider>.

    ```csharp
    [Import]
    internal SVsServiceProvider ServiceProvider = null;
    ```

5. V `GetClassifier()` metodu, přidejte následující kód před `return` – příkaz:

    ```csharp
   DTE dte = (DTE)ServiceProvider.GetService(typeof(DTE));
   ```

::: moniker-end

## <a name="see-also"></a>Viz také:

- [Jazykové služby a editor Rozšiřovací body](../extensibility/language-service-and-editor-extension-points.md)
- [Spusťte sadu Visual Studio pomocí DTE](launch-visual-studio-dte.md)