---
title: 'Návod: Propojení typu obsahu příponu názvu souboru | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], new - link content type to file name extension
ms.assetid: 21ee64ce-9afe-4b08-94a0-8389cc4dc67c
caps.latest.revision: 25
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: beae9d0526cb9f2f294f2267a8da52d3ce3d8c08
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68201999"
---
# <a name="walkthrough-linking-a-content-type-to-a-file-name-extension"></a>Návod: Propojení typu obsahu s příponou názvu souboru
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Můžete definovat vlastní typ obsahu a odkaz na něj příponu názvu souboru s použitím rozšíření editoru Managed Extensibility Framework (MEF). V některých případech již byl definován příponu názvu souboru službou jazyka. Nicméně pomocí MEF je stále třeba propojit ho typu obsahu.  
  
## <a name="prerequisites"></a>Požadavky  
 Spouští se v sadě Visual Studio 2015, nenainstalujete sadu Visual Studio SDK ze služby Stažení softwaru. Je zahrnut jako volitelná funkce v instalačním programu sady Visual Studio. VS SDK můžete také nainstalovat později. Další informace najdete v tématu [instalace sady Visual Studio SDK](../extensibility/installing-the-visual-studio-sdk.md).  
  
## <a name="creating-a-mef-project"></a>Vytvoření projektu rozhraní MEF  
  
1. Vytvořte projekt VSIX C#. (V **nový projekt** dialogového okna, vyberte **Visual C# / rozšíření**, pak **projekt VSIX**.) Pojmenujte řešení `ContentTypeTest`.  
  
2. V **source.extension.vsixmanifest** souboru, přejděte na **prostředky** kartu a nastavit **typ** pole **Microsoft.VisualStudio.MefComponent**, **zdroj** pole **projekt v aktuálním řešení**a **projektu** pole pro název projektu.  
  
## <a name="defining-the-content-type"></a>Definování typu obsahu  
  
1. Přidejte soubor třídy a pojmenujte ho `FileAndContentTypes`.  
  
2. Přidejte odkazy na následující sestavení:  
  
    1. System.ComponentModel.Composition  
  
    2. Microsoft.VisualStudio.Text.Logic  
  
    3. Microsoft.VisualStudio.CoreUtility  
  
3. Přidejte následující `using` direktivy.  
  
    ```csharp  
    using System.ComponentModel.Composition;  
    using Microsoft.VisualStudio.Text.Classification;  
    using Microsoft.VisualStudio.Utilities;  
  
    ```  
  
4. Deklarujte statickou třídu, která obsahuje definice.  
  
    ```csharp  
    internal static class FileAndContentTypeDefinitions  
    {. . .}  
    ```  
  
5. V této třídě exportovat <xref:Microsoft.VisualStudio.Utilities.ContentTypeDefinition> s názvem "hid" a deklarovat jeho základní definici, aby se "text".  
  
    ```csharp  
    internal static class FileAndContentTypeDefinitions  
    {  
        [Export]  
        [Name("hid")]  
        [BaseDefinition("text")]  
        internal static ContentTypeDefinition hidingContentTypeDefinition;  
    }  
    ```  
  
## <a name="linking-a-file-name-extension-to-a-content-type"></a>Propojení příponu názvu souboru na typ obsahu  
  
- Pokud chcete namapovat příponu názvu souboru tohoto typu obsahu, exportovat <xref:Microsoft.VisualStudio.Utilities.FileExtensionToContentTypeDefinition> , který má příponu "HID" a typu obsahu "hid".  
  
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
  
## <a name="adding-the-content-type-to-an-editor-export"></a>Přidávání do editoru Export typu obsahu  
  
1. Vytvoření rozšíření editoru. Například můžete použít rozšíření piktogram okraj, je popsáno v [názorný postup: Vytvoření okrajového piktogramu](../extensibility/walkthrough-creating-a-margin-glyph.md).  
  
2. Přidání třídy, které jste definovali v tomto postupu.  
  
3. Při exportu rozšíření třídy, přidejte <xref:Microsoft.VisualStudio.Utilities.ContentTypeAttribute> typu "hid" k němu.  
  
    ```csharp  
    [Export]  
    [ContentType("hid")]  
    ```  
  
## <a name="see-also"></a>Viz také  
 [Rozšiřovací body služeb jazyka a editoru](../extensibility/language-service-and-editor-extension-points.md)
