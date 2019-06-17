---
title: Způsoby, jak ladit kód XSLT
ms.date: 03/05/2019
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
ms.workload:
- multiple
ms.openlocfilehash: 67ea95e3c52daed03acfe451f353edc039e1fecb
ms.sourcegitcommit: 9753c7544cec852ca5efd0834e0956d9e53a5734
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/13/2019
ms.locfileid: "67043532"
---
# <a name="debugging-xslt"></a>Ladění XSLT

Můžete ladit kód XSLT v sadě Visual Studio. Soubor XSLT ladicí program podporuje nastavení zarážek, zobrazení stavů provedení transformace XSLT a tak dále. Ladicí program XSLT slouží k ladění šablon stylů XSLT nebo XSLT aplikací.

Krokování s vnořením do krokování přes nebo krokování mimo kód můžete spustit jeden řádek kódu v čase. Příkazy pro použití funkce krokování kódu v ladicím programu XSLT jsou že stejné jako u sady Visual Studio ladicí programy.

Po spuštění ladění otevře ladicí program XSLT windows lze zobrazit, že vstupní dokument a XSLT výstupu.

> [!NOTE]
> Ladicí program XSLT je pouze k dispozici v edicích sady Visual Studio Professional a Enterprise.

## <a name="debug-from-the-xml-editor"></a>Ladění z editoru XML

Ladicí program můžete spustit, když máte šablony stylů nebo vstupní soubor XML, otevřete v editoru. To umožňuje ladění během navrhování šablony stylů.

1. Otevření šablony stylů nebo soubor XML v sadě Visual Studio.

1. Vyberte **spustit ladění XSLT** z **XML** nabídky nebo stisknutím klávesy **Alt**+**F5**.

## <a name="debug-from-an-app-that-uses-xslt"></a>Ladění z aplikace, který používá XSLT

Můžete krokovat s vnořením XSLT při ladění aplikace. Když stisknete klávesu **F11** na <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A?displayProperty=fullName> volání ladicího programu můžete krokovat s vnořením kód XSLT.

> [!NOTE]
> Krokování s vnořením do XSLT z <xref:System.Xml.Xsl.XslTransform> třída není podporována. <xref:System.Xml.Xsl.XslCompiledTransform> Třídy je pouze procesoru XSLT, který podporuje krokování XSLT, při ladění.

### <a name="to-start-debugging-an-xslt-application"></a>Pro spuštění ladění XSLT aplikace

1. Při vytváření instance <xref:System.Xml.Xsl.XslCompiledTransform> objektu, nastaven `enableDebug` parametr `true` ve vašem kódu. Říká, že procesoru XSLT se vytvářet i informace o ladění při kompilaci kódu.

1. Stisknutím klávesy **F11** k krokování s vnořením do kódu XSLT.

   Šablony stylů XSLT je načten v novém okně dokumentu a spustí ladicí program XSLT.

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
    private const string stylesheet = @"c:\data\xsl_files\below-average.xsl";
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

## <a name="xslt-profiler"></a>Profiler XSLT

[XSLT profiler](../xml-tools/xslt-profiler.md) je nástroj, který umožňuje vývojářům měřit, vyhodnotit a řešit problémy související s výkonem v XSLT kódu tak, že vytvoříte podrobné sestavy o výkonu XSLT. Další informace najdete v tématu [XSLT profiler](../xml-tools/xslt-profiler.md).

## <a name="see-also"></a>Viz také:

- [Návod: Ladění stylů XSLT](../xml-tools/walkthrough-debug-an-xslt-style-sheet.md)
- [První pohled na ladicího programu sady Visual Studio](../debugger/debugger-feature-tour.md)
- [Základní informace o ladění: Zarážky](../debugger/using-breakpoints.md)
