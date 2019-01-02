---
title: 'Postupy: Spuštění ladění XSLT'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
dev_langs:
- CSharp
ms.workload:
- multiple
ms.openlocfilehash: 170d4d3d0c952e13a5fefb74b23536f50be1e9a6
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53925128"
---
# <a name="how-to-start-debugging-xslt"></a>Postupy: Spuštění ladění XSLT

Ladicí program XSLT slouží k ladění šablony stylů XSLT nebo z některé aplikace XSLT. Při ladění, můžete spustit jeden řádek kódu v čase krokování s vnořením do krokování přes nebo Krokování ven z kódu. Příkazy pro funkci krokování kódu jsou že stejné pro ladicí program XSLT jako u sady Visual Studio ladicí programy. Po spuštění ladění otevře ladicí program XSLT windows lze zobrazit, že vstupní dokument a XSLT výstupu.

## <a name="xml-editor"></a>Editor XML

Ladicí program lze spustit z editoru XML. To umožňuje ladit, jako jsou návrh šablony stylů.

### <a name="to-start-debugging-from-a-style-sheet"></a>Spuštění ladění od šablony stylů

1. Otevření šablony stylů v editoru XML.

1. Vyberte **ladění XSL** z **XML** nabídky.

### <a name="to-start-debugging-from-an-xml-input-document"></a>Spuštění ladění od vstupní dokument XML

1. Otevřete dokument XML v editoru XML.

1. Vyberte **ladění XSL** z **XML** nabídky.

## <a name="xslt-from-other-languages"></a>Transformace XSLT z jiných jazyků

Můžete také Krokovat s vnořením XSLT při ladění aplikace. Po stisknutí klávesy F11 <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A?displayProperty=fullName> volání ladicího programu můžete krokovat s vnořením kód XSLT.

> [!NOTE]
> Krokování s vnořením do XSLT z <xref:System.Xml.Xsl.XslTransform> třída není podporována. <xref:System.Xml.Xsl.XslCompiledTransform> Třídy je pouze procesoru XSLT, který podporuje krokování XSLT, při ladění.

### <a name="to-start-debugging-an-xslt-application"></a>Pro spuštění ladění XSLT aplikace

1. Při vytváření instance <xref:System.Xml.Xsl.XslCompiledTransform> objektu, nastaven `enableDebug` parametr `true` ve vašem kódu.

     Říká, že procesoru XSLT se vytvářet i informace o ladění při kompilaci kódu.

1. Stisknutím klávesy F11 lze přepínat mezi Krokovat s vnořením kód XSLT.

     Šablony stylů XSLT je načten v novém okně dokumentu a ladicí program XSLT je spuštěn.

     Alternativně můžete přidat přerušení k šabloně stylů a spusťte aplikaci.

### <a name="example"></a>Příklad

Následuje příklad programu v jazyce C# XSLT. Ukazuje, jak povolit ladění XSLT.

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

## <a name="see-also"></a>Viz také:

- [Návod: Ladění stylů XSLT](../xml-tools/walkthrough-debug-an-xslt-style-sheet.md)
- [První seznámení s ladicím programem](../debugger/debugger-feature-tour.md)   