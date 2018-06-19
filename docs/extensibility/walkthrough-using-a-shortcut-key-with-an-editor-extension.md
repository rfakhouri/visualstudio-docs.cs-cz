---
title: 'Návod: Použití klávesovou zkratku s příponou Editor | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], new - link keystrokes to commands
ms.assetid: cf6cc6c6-5a65-4f90-8f14-663decf74672
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: f8f8a310832f0691b4bc4056baddeb1fbbad78f8
ms.sourcegitcommit: fe5a72bc4c291500f0bf4d6e0778107eb8c905f5
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/07/2018
ms.locfileid: "33704022"
---
# <a name="walkthrough-using-a-shortcut-key-with-an-editor-extension"></a>Návod: Použití klávesovou zkratku s příponou editoru
Může reagovat na klávesové zkratky v editoru rozšíření. Následující postup ukazuje, jak přidat dalších úprav zobrazení textového zobrazení pomocí klávesové zkratky. Tento názorný postup je založený na šabloně zobrazení dalších úprav editoru a umožňuje přidat dalších úprav pomocí + znak.  
  
## <a name="prerequisites"></a>Požadavky  
 Od sady Visual Studio 2015 se neinstalovat sadu Visual Studio SDK z webu Stažení softwaru. Je zahrnuta jako volitelná funkce v instalačním programu sady Visual Studio. VS SDK můžete také nainstalovat později. Další informace najdete v tématu [instalace sady Visual Studio SDK](../extensibility/installing-the-visual-studio-sdk.md).  
  
## <a name="creating-a-managed-extensibility-framework-mef-project"></a>Vytvoření projektu spravovaných rozšíření Framework (MEF)  
  
1.  Vytvoření projektu C# VSIX. (V **nový projekt** dialogovém okně, vyberte **Visual C# nebo rozšíření**, pak **projektu VSIX**.) Název řešení `KeyBindingTest`.  
  
2.  Do projektu přidejte šablony položky dalších úprav editoru textu a pojmenujte ji `KeyBindingTest`. Další informace najdete v tématu [vytváření rozšíření pomocí šablony položky Editor](../extensibility/creating-an-extension-with-an-editor-item-template.md).  
  
3.  Přidejte následující odkazy a nastavte **CopyLocal** k `false`:  
  
     Microsoft.VisualStudio.Editor  
  
     Sestavení Microsoft.VisualStudio.OLE.Interop  
  
     Microsoft.VisualStudio.Shell.14.0  
  
     Microsoft.VisualStudio.TextManager.Interop  
  
 V souboru třídy KeyBindingTest změňte název třídy pro PurpleCornerBox. Pomocí žárovky, který se zobrazí na levém okraji provést potřebné změny. V konstruktoru, změňte název vrstvy dalších úprav z **KeyBindingTest** k **PurpleCornerBox**:  
  
```csharp  
this.layer = view.GetAdornmentLayer("PurpleCornerBox");  
```  

V souboru třídy KeyBindingTestTextViewCreationListener.cs, změnit název AdornmentLayer z **KeyBindingTest** k **PurpleCornerBox**:
  
    ```csharp  
    [Export(typeof(AdornmentLayerDefinition))]  
    [Name("PurpleCornerBox")]  
    [Order(After = PredefinedAdornmentLayers.Selection, Before = PredefinedAdornmentLayers.Text)]  
    public AdornmentLayerDefinition editorAdornmentLayer;  
    ```  

## <a name="handling-typechar-command"></a>Příkaz TYPECHAR zpracování
Před Visual Studio 2017 verze 15,6 operací byl jediný způsob, jak zpracování příkazů v editoru rozšíření implementace <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> na základě filtru příkaz. Visual Studio 2017 verze 15,6 operací zavedl moderní zjednodušené přístup založený na obslužné rutiny příkazů editoru. V následujících dvou částech ukazují, jak zpracovat příkaz pomocí jak starší verze a moderní přístup.

## <a name="defining-the-command-filter-prior-to-visual-studio-2017-version-156"></a>Definování příkazu filtru (před verzí Visual Studio 2017 verze 15,6 operací)

 Příkaz filtru je implementací <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>, která zpracovává příkaz po vytvoření instance dalších úprav.  
  
1.  Přidejte soubor třídy a pojmenujte ji `KeyBindingCommandFilter`.  
  
2.  Přidejte následující příkazy using.  
  
    ```csharp  
    using System;  
    using System.Runtime.InteropServices;  
    using Microsoft.VisualStudio.OLE.Interop;  
    using Microsoft.VisualStudio;  
    using Microsoft.VisualStudio.Text.Editor;  
  
    ```  
  
3.  Třída s názvem KeyBindingCommandFilter musí dědit z <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>.  
  
    ```csharp  
    internal class KeyBindingCommandFilter : IOleCommandTarget  
    ```  
  
4.  Přidejte privátním polím pro textového zobrazení, další příkaz v řetězu příkaz a příznak představující zda příkaz Filtr byl již přidán.  
  
    ```csharp  
    private IWpfTextView m_textView;  
    internal IOleCommandTarget m_nextTarget;  
    internal bool m_added;  
    internal bool m_adorned;  
    ```  
  
5.  Přidejte konstruktor, který nastaví textového zobrazení.  
  
    ```csharp  
    public KeyBindingCommandFilter(IWpfTextView textView)  
    {  
        m_textView = textView;  
        m_adorned = false;  
    }  
    ```  
  
6.  Implementace `QueryStatus()` metoda následujícím způsobem.  
  
    ```csharp  
    int IOleCommandTarget.QueryStatus(ref Guid pguidCmdGroup, uint cCmds, OLECMD[] prgCmds, IntPtr pCmdText)  
    {  
        return m_nextTarget.QueryStatus(ref pguidCmdGroup, cCmds, prgCmds, pCmdText);  
    }  
    ```  
  
7.  Implementace `Exec()` metody, které se přidá fialové pole do zobrazení, pokud + zadání znaku.  
  
    ```csharp  
    int IOleCommandTarget.Exec(ref Guid pguidCmdGroup, uint nCmdID, uint nCmdexecopt, IntPtr pvaIn, IntPtr pvaOut)  
    {  
        if (m_adorned == false)  
        {  
            char typedChar = char.MinValue;  
  
            if (pguidCmdGroup == VSConstants.VSStd2K && nCmdID == (uint)VSConstants.VSStd2KCmdID.TYPECHAR)  
            {  
                typedChar = (char)(ushort)Marshal.GetObjectForNativeVariant(pvaIn);  
                if (typedChar.Equals('+'))  
                {  
                    new PurpleCornerBox(m_textView);  
                    m_adorned = true;  
                }  
            }  
        }  
        return m_nextTarget.Exec(ref pguidCmdGroup, nCmdID, nCmdexecopt, pvaIn, pvaOut);  
    }  
  
    ```  
  
## <a name="adding-the-command-filter-prior-to-visual-studio-2017-version-156"></a>Přidání filtru příkazu (před verzí Visual Studio 2017 verze 15,6 operací)
 Zprostředkovatel dalších úprav musíte přidat příkaz filtru do textového zobrazení. V tomto příkladu se implementuje poskytovatele <xref:Microsoft.VisualStudio.Editor.IVsTextViewCreationListener> pro naslouchání na události vytváření zobrazení textu. Tento zprostředkovatel dalších úprav zároveň exportuje dalších úprav vrstvu, která definuje pořadí dalších úprav.  
  
1.  V souboru KeyBindingTestTextViewCreationListener, přidejte následující příkazy:  
  
    ```csharp  
    using System;  
    using System.Collections.Generic;  
    using System.ComponentModel.Composition;  
    using Microsoft.VisualStudio;  
    using Microsoft.VisualStudio.OLE.Interop;  
    using Microsoft.VisualStudio.Utilities;  
    using Microsoft.VisualStudio.Editor;  
    using Microsoft.VisualStudio.Text.Editor;  
    using Microsoft.VisualStudio.TextManager.Interop;  
  
    ```  
  
2.  Chcete-li získat adaptér zobrazení textu, je nutné importovat <xref:Microsoft.VisualStudio.Editor.IVsEditorAdaptersFactoryService>.  
  
    ```csharp  
    [Import(typeof(IVsEditorAdaptersFactoryService))]  
    internal IVsEditorAdaptersFactoryService editorFactory = null;  
  
    ```  
  
3.  Změna <xref:Microsoft.VisualStudio.Text.Editor.IWpfTextViewCreationListener.TextViewCreated%2A> metody, které se přidá `KeyBindingCommandFilter`.  
  
    ```csharp  
    public void TextViewCreated(IWpfTextView textView)  
    {  
        AddCommandFilter(textView, new KeyBindingCommandFilter(textView));  
    }  
    ```  
  
4.  `AddCommandFilter` Obslužná rutina získá adaptér zobrazení textu a přidá filtr příkaz.  
  
    ```csharp  
    void AddCommandFilter(IWpfTextView textView, KeyBindingCommandFilter commandFilter)  
    {  
        if (commandFilter.m_added == false)  
        {  
            //get the view adapter from the editor factory  
            IOleCommandTarget next;   
            IVsTextView view = editorFactory.GetViewAdapter(textView);  
  
            int hr = view.AddCommandFilter(commandFilter, out next);  
  
            if (hr == VSConstants.S_OK)  
            {      
                commandFilter.m_added = true;  
                 //you'll need the next target for Exec and QueryStatus   
                if (next != null)  
                commandFilter.m_nextTarget = next;  
            }  
        }  
    }  
    ```  

## <a name="implement-a-command-handler-starting-in-visual-studio-2017-version-156"></a>Implementace obslužná rutina příkazu (počínaje Visual Studio 2017 verze 15,6 operací)

Nejdřív aktualizujte odkazy Nuget projektu tak, aby odkazovaly editoru nejnovější rozhraní API:

1. Klikněte pravým tlačítkem na projekt a vyberte **spravovat balíčky Nuget**.

2. V **Správce balíčků Nuget**, vyberte **aktualizace** vyberte **vybrat všechny balíčky** zaškrtávací políčko a potom vyberte **aktualizace**.

Obslužná rutina je implementací <xref:Microsoft.VisualStudio.Commanding.ICommandHandler%601>, která zpracovává příkaz po vytvoření instance dalších úprav.  
  
1.  Přidejte soubor třídy a pojmenujte ji `KeyBindingCommandHandler`.  
  
2.  Přidejte následující příkazy using.  
  
    ```csharp  
    using Microsoft.VisualStudio.Commanding;
    using Microsoft.VisualStudio.Text.Editor;
    using Microsoft.VisualStudio.Text.Editor.Commanding.Commands;
    using Microsoft.VisualStudio.Utilities;
    using System.ComponentModel.Composition;   
    ```  
  
3.  Třída s názvem KeyBindingCommandHandler musí dědit z `ICommandHandler<TypeCharCommandArgs>`a exportovat je jako <xref:Microsoft.VisualStudio.Commanding.ICommandHandler>:
  
    ```csharp  
    [Export(typeof(ICommandHandler))]
    [ContentType("text")]
    [Name("KeyBindingTest")]
    internal class KeyBindingCommandHandler : ICommandHandler<TypeCharCommandArgs>  
    ```  
  
4.  Přidejte zobrazovaný název obslužná rutina příkazu:  
  
    ```csharp  
    public string DisplayName => "KeyBindingTest";
    ```  
    
5.  Implementace `GetCommandState()` metoda následujícím způsobem. Protože tato obslužná rutina zpracovává základní příkaz TYPECHAR editor, můžete delegovat, povolení příkazu editoru jádra.
  
    ```csharp  
    public CommandState GetCommandState(TypeCharCommandArgs args)
    {
        return CommandState.Unspecified;
    } 
    ```  
  
6.  Implementace `ExecuteCommand()` metody, které se přidá fialové pole do zobrazení, pokud + zadání znaku. 
  
    ```csharp  
    public bool ExecuteCommand(TypeCharCommandArgs args, CommandExecutionContext executionContext)
    {
        if (args.TypedChar == '+')
        {
            bool alreadyAdorned = args.TextView.Properties.TryGetProperty(
                "KeyBindingTextAdorned", out bool adorned) && adorned;
            if (!alreadyAdorned)
            {
                new PurpleCornerBox((IWpfTextView)args.TextView);
                args.TextView.Properties.AddProperty("KeyBindingTextAdorned", true);
            }
        }

        return false;
    }
    ```  
 7. Zkopírujte definice dalších úprav vrstvy ze souboru KeyBindingTestTextViewCreationListener.cs do KeyBindingCommandHandler.cs a následně odstranit soubor KeyBindingTestTextViewCreationListener.cs:
 
    ```csharp  
    /// <summary>
    /// Defines the adornment layer for the adornment. This layer is ordered
    /// after the selection layer in the Z-order.
    /// </summary>
    [Export(typeof(AdornmentLayerDefinition))]
    [Name("PurpleCornerBox")]
    [Order(After = PredefinedAdornmentLayers.Selection, Before = PredefinedAdornmentLayers.Text)]
    private AdornmentLayerDefinition editorAdornmentLayer;    
    ```  

## <a name="making-the-adornment-appear-on-every-line"></a>Provádění dalších úprav zobrazí na každém řádku  

Původní dalších úprav zobrazovaly na každý znak "a" do textového souboru. Teď, když jsme změnili kódu k přidání dalších úprav v reakci na znak '+', přidá jenom na řádku dalších úprav kde '+' je zadán. Nemůžeme kód dalších úprav změnit tak, aby jednou dalších úprav se zobrazí na každé "a".  
  
V souboru KeyBindingTest.cs změňte metodu CreateVisuals() k iteraci v rámci všechny řádky v zobrazení pro uspořádání "a" znak.  
  
```csharp  
private void CreateVisuals(ITextViewLine line)  
{  
    IWpfTextViewLineCollection textViewLines = this.view.TextViewLines;  
  
    foreach (ITextViewLine textViewLine in textViewLines)  
    {  
        if (textViewLine.ToString().Contains("a"))  
        {  
            // Loop through each character, and place a box around any 'a'   
            for (int charIndex = textViewLine.Start; charIndex < textViewLine.End; charIndex++)  
            {  
                if (this.view.TextSnapshot[charIndex] == 'a')  
                {  
                    SnapshotSpan span = new SnapshotSpan(this.view.TextSnapshot, Span.FromBounds(charIndex, charIndex + 1));  
                    Geometry geometry = textViewLines.GetMarkerGeometry(span);  
                    if (geometry != null)  
                    {  
                        var drawing = new GeometryDrawing(this.brush, this.pen, geometry);  
                        drawing.Freeze();  
  
                        var drawingImage = new DrawingImage(drawing);  
                        drawingImage.Freeze();  
  
                        var image = new Image  
                        {  
                            Source = drawingImage,  
                        };  
  
                        // Align the image with the top of the bounds of the text geometry  
                        Canvas.SetLeft(image, geometry.Bounds.Left);  
                        Canvas.SetTop(image, geometry.Bounds.Top);  
  
                        this.layer.AddAdornment(AdornmentPositioningBehavior.TextRelative, span, null, image, null);  
                    }  
                }  
            }  
        }  
    }  
}  
```  
  
## <a name="building-and-testing-the-code"></a>Vytváření a testování kódu  
  
1.  Sestavte řešení KeyBindingTest a spustíte ho v experimentální instanci.  
  
2.  Vytvořte nebo otevřete textový soubor. Zadejte některé slova, která obsahuje znak "a" a pak zadejte + kdekoli v zobrazení textu.  
  
     Fialové čtverce by se zobrazit na každý "a" znak v souboru.
