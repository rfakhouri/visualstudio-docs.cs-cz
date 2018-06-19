---
title: 'Návod: Propojení typu obsahu s příponu názvu souboru | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], new - link content type to file name extension
ms.assetid: 21ee64ce-9afe-4b08-94a0-8389cc4dc67c
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: cca12f7c04b51bcf2b695e00d9305a7feb72ebc4
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31144892"
---
# <a name="walkthrough-linking-a-content-type-to-a-file-name-extension"></a>Návod: Propojení typu obsahu s příponu názvu souboru
Můžete definovat vlastní typu obsahu a propojení příponu názvu souboru k němu pomocí rozšíření editorů Managed Extensibility Framework (MEF). V některých případech již byl definován příponu názvu souboru službou jazyk. Nicméně pro použití s MEF musíte stále propojit je typ obsahu.  
  
## <a name="prerequisites"></a>Požadavky  
 Od sady Visual Studio 2015 se neinstalovat sadu Visual Studio SDK z webu Stažení softwaru. Je zahrnuta jako volitelná funkce v instalačním programu sady Visual Studio. VS SDK můžete také nainstalovat později. Další informace najdete v tématu [instalace sady Visual Studio SDK](../extensibility/installing-the-visual-studio-sdk.md).  
  
## <a name="creating-a-mef-project"></a>Vytvoření projektu MEF  
  
1.  Vytvoření projektu C# VSIX. (V **nový projekt** dialogovém okně, vyberte **Visual C# nebo rozšíření**, pak **projektu VSIX**.) Název řešení `ContentTypeTest`.  
  
2.  V **source.extension.vsixmanifest** souboru, přejděte na **prostředky** kartě a nastavte **typ** do **Microsoft.VisualStudio.MefComponent**, **zdroj** do **na projekt v aktuálním řešení**a **projektu** pole na název projektu.  
  
## <a name="defining-the-content-type"></a>Definování typu obsahu  
  
1.  Přidejte soubor třídy a pojmenujte ji `FileAndContentTypes`.  
  
2.  Přidejte odkazy na následující sestavení:  
  
    1.  System.ComponentModel.Composition  
  
    2.  Microsoft.VisualStudio.Text.Logic  
  
    3.  Microsoft.VisualStudio.CoreUtility  
  
3.  Přidejte následující `using` direktivy.  
  
    ```csharp  
    using System.ComponentModel.Composition;  
    using Microsoft.VisualStudio.Text.Classification;  
    using Microsoft.VisualStudio.Utilities;  
  
    ```  
  
4.  Deklarujte statickou třídu, která obsahuje definice.  
  
    ```csharp  
    internal static class FileAndContentTypeDefinitions  
    {. . .}  
    ```  
  
5.  V této třídě exportovat <xref:Microsoft.VisualStudio.Utilities.ContentTypeDefinition> s názvem "hid" a jeho základní definice jako "text" deklarovat.  
  
    ```csharp  
    internal static class FileAndContentTypeDefinitions  
    {  
        [Export]  
        [Name("hid")]  
        [BaseDefinition("text")]  
        internal static ContentTypeDefinition hidingContentTypeDefinition;  
    }  
    ```  
  
## <a name="linking-a-file-name-extension-to-a-content-type"></a>Propojování příponu názvu souboru na typ obsahu  
  
-   Tento typ obsahu mapovat příponu názvu souboru, exportovat <xref:Microsoft.VisualStudio.Utilities.FileExtensionToContentTypeDefinition> s příponou "HID" a typu obsahu "hid".  
  
    ```csharp  
    internal static class FileAndContentTypeDefinitions  
    {  
         [Export]  
         [Name("hid")]  
         [BaseDefinition("text")]  
        internal static ContentTypeDefinition hidingContentTypeDefinition;  
  
         [Export]  
         [FileExtension(".hid")]  
         [ContentType("hid")]  
        internal static FileExtensionToContentTypeDefinition hiddenFileExtensionDefinition;  
    }  
    ```  
  
## <a name="adding-the-content-type-to-an-editor-export"></a>Přidání typu obsahu pro Export editoru  
  
1.  Vytváření rozšíření editoru. Například můžete použít rozšíření glyfy okraj popsané v [návod: vytváření glyf okraj](../extensibility/walkthrough-creating-a-margin-glyph.md).  
  
2.  Přidáte třídy, na kterou jste definovali v tomto postupu.  
  
3.  Pokud exportujete rozšíření třídy, přidejte <xref:Microsoft.VisualStudio.Utilities.ContentTypeAttribute> typu "hid" k němu.  
  
    ```csharp  
    [Export]  
    [ContentType("hid")]  
    ```  
  
## <a name="see-also"></a>Viz také  
 [Rozšiřovací body služeb jazyka a editoru](../extensibility/language-service-and-editor-extension-points.md)