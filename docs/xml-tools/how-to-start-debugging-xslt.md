---
title: 'Postupy: spuštění ladění XSLT | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-general
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
dev_langs:
- CSharp
ms.workload:
- multiple
ms.openlocfilehash: f76412ce4dd0f5d443564755c460dfb82c186847
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-start-debugging-xslt"></a>Postupy: spuštění ladění XSLT

Ladicí program XSLT slouží k ladění stylů XSLT nebo XSLT aplikaci. Při ladění, můžete provést jeden řádek kódu současně zanoříte se do, krokování přes nebo krokování s mimo kód. Příkazy využívat funkce krokování kódu jsou že stejné pro ladicí program XSLT jako u jiných sady Visual Studio ladicí programy. Po spuštění ladění, otevře se XSLT ladicího programu windows, které ukazují, že vstupní dokument a XSLT výstup.

## <a name="xml-editor"></a>XML Editor

Ladicí program lze spustit z editoru XML. To umožňuje ladění jako navrhujete šablony stylů.

### <a name="to-start-debugging-from-a-style-sheet"></a>Spustit ladění ze šablony stylů

1. Otevřete v editoru XML šablony stylů.

1. Vyberte **ladění XSL** z **XML** nabídky.

### <a name="to-start-debugging-from-an-xml-input-document"></a>Spustit ladění ze vstupní dokument XML

1. Otevřete dokument XML v editoru XML.

1. Vyberte **ladění XSL** z **XML** nabídky.

## <a name="xslt-from-other-languages"></a>XSLT z jiných jazyků

Můžete taky krok do XSLT při ladění aplikace. Po stisknutí klávesy F11 <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A?displayProperty=fullName> volání do kódu XSLT můžete krok ladicího programu.

> [!NOTE]
> Zanoříte se do XSLT z <xref:System.Xml.Xsl.XslTransform> třída není podporována. <xref:System.Xml.Xsl.XslCompiledTransform> Třída je pouze XSLT procesor, který podporuje zanoříte se do XSLT při ladění.

### <a name="to-start-debugging-an-xslt-application"></a>Spustit ladění aplikace XSLT

1. Při vytváření instance <xref:System.Xml.Xsl.XslCompiledTransform> objektu, nastavte `enableDebug` parametru `true` v kódu.

     Tato hodnota informuje XSLT procesor pro vytvoření informace o ladění při kompilaci kódu.

1. Stisknutím klávesy F11 přejde do kódu XSLT.

     Styl XSLT je načten do nového okna dokumentu a ladicí program XSLT je spuštěná.

     Alternativně můžete přidat bod rozdělení do šablony stylů a spusťte aplikaci.

### <a name="example"></a>Příklad

Následuje příklad programu v C# XSLT. Ukazuje, jak povolit ladění XSLT.

```csharp
using System;  
using System.IO;  
using System.Xml;  
using System.Xml.Xsl;  
  
namespace ConsoleApplication   
{  
  class Program   
  {  
    private const string sourceFile = @"c:\data\xsl_files\books.xml";  
    private const string stylesheet = @"c:\data\xsl_files\belowAvg.xsl";  
    private const string outputFile = @"c:\data\xsl_files\output.xml";  
  
    static void Main(string[] args)  
    {  
      // Enable XSLT debugging.
      XslCompiledTransform xslt = new XslCompiledTransform(true);  
  
      // Compile the style sheet.
      xslt.Load(stylesheet)  
  
      // Execute the XSLT transform.
      FileStream outputStream = new FileStream(outputFile, FileMode.Append);  
      xslt.Transform(sourceFile, null, outputStream);  
    }  
  }  
}  
```

## <a name="see-also"></a>Viz také

[Návod: Ladění šablony stylů XSLT](../xml-tools/walkthrough-debug-an-xslt-style-sheet.md)  
[Základy ladicího programu](../debugger/debugger-basics.md)