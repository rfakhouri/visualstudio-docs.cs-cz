---
title: Návod k analýze spravovaného kódu pro vady kódu | Microsoft Docs
ms.date: 01/29/2018
ms.topic: conceptual
helpviewer_keywords:
- code analysis [Visual Studio]
- managed code, analyzing
author: mikadumont
ms.author: midumont
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: 4a00fdb2a41a03554113f2ecb626185aab2c74d5
ms.sourcegitcommit: 209ed0fcbb8daa1685e8d6b9a97f3857a4ce1152
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/16/2019
ms.locfileid: "69547994"
---
# <a name="walkthrough-use-static-code-analysis-to-find-code-defects"></a>Návod: Hledání vad kódu pomocí statické analýzy kódu

V tomto návodu budete analyzovat spravovaný projekt pro vady kódu pomocí nástroje Analýza kódu starší verze.

Tento článek vás provede procesem použití starší verze analýzy k analýze sestavení spravovaného kódu .NET pro účely souladu s pokyny pro návrh .NET.

## <a name="create-a-class-library"></a>Vytvoření knihovny tříd

### <a name="to-create-a-class-library"></a>Vytvoření knihovny tříd

1. Na **souboru** nabídce zvolte **nový** > **projektu**.

1. V dialogovém **okně Nový projekt** rozbalte položku nainstalovaná > **aplikace C#Visual** a pak zvolte možnost **plocha systému Windows**.

1. Vyberte šablonu **knihovny tříd (.NET Framework)** .

1. Do textového pole **název** zadejte **CodeAnalysisManagedDemo** a pak klikněte na **OK**.

1. Po vytvoření projektu otevřete soubor *Class1.cs* .

1. Existující text v Class1.cs nahraďte následujícím kódem:

   ```csharp
   using System;

   namespace testCode
   {
       public class demo : Exception
       {
           public static void Initialize(int size) { }
           protected static readonly int _item;
           public static int item { get { return _item; } }
       }
   }
   ```

1. Uložte soubor Class1.cs.

## <a name="analyze-the-project"></a>Analyzovat projekt

### <a name="to-analyze-a-managed-project-for-code-defects"></a>Analýza spravovaného projektu pro vady kódu

1. Vyberte projekt CodeAnalysisManagedDemo v **Průzkumník řešení**.

1. V nabídce **projekt** klikněte na příkaz **vlastnosti**.

     Zobrazí se stránka vlastnosti CodeAnalysisManagedDemo.

1. Klikněte na kartu **Analýza kódu** .

1. Ujistěte se, že je zaškrtnuté políčko **Povolit analýzu kódu při sestavení** .

1. V rozevíracím seznamu **Spustit tuto sadu pravidel** vyberte možnost **Microsoft všechna pravidla**.

1. V nabídce **soubor** klikněte na příkaz **Uložit vybrané položky**a poté zavřete stránky vlastnosti.

1. V nabídce **sestavení** klikněte na příkaz **sestavit CodeAnalysisManagedDemo**.

    Upozornění sestavení projektu CodeAnalysisManagedDemo se zobrazují v oknech **Seznam chyb** a **výstup** .

## <a name="correct-the-code-analysis-issues"></a>Opravte potíže s analýzou kódu

### <a name="to-correct-code-analysis-rule-violations"></a>Oprava porušení pravidel pro analýzu kódu

1. V nabídce **zobrazení** vyberte možnost **Seznam chyb**.

    V závislosti na zvoleném profilu vývojáře možná budete muset v nabídce **zobrazení** Ukázat na **jiné okna** a pak vybrat **Seznam chyb**.

1. V **Průzkumník řešení**vyberte možnost **Zobrazit všechny soubory**.

1. Rozbalte uzel vlastnosti a pak otevřete soubor *AssemblyInfo.cs* .

1. Upozornění můžete opravit pomocí následujících tipů:

   [CA1014: Označte sestavení pomocí CLSCompliantAttribute](../code-quality/ca1014-mark-assemblies-with-clscompliantattribute.md): Microsoft. Design: demo by měla být označená CLSCompliantAttribute a její hodnota by měla být true.

   1. Přidejte kód `using System;` do souboru AssemblyInfo.cs.

   1. Dále přidejte kód `[assembly: CLSCompliant(true)]` na konec souboru AssemblyInfo.cs.

   [CA1032: Implementujte standardní konstruktory](../code-quality/ca1032-implement-standard-exception-constructors.md)výjimky: Microsoft.Design: Do této třídy přidejte následující konstruktor: public demo (String)

   1. Přidejte konstruktor `public demo (String s) : base(s) { }` do třídy `demo`.

   [CA1032: Implementujte standardní konstruktory](../code-quality/ca1032-implement-standard-exception-constructors.md)výjimky: Microsoft.Design: Do této třídy přidejte následující konstruktor: public demo (řetězec, výjimka)

   1. Přidejte konstruktor `public demo (String s, Exception e) : base(s, e) { }` do třídy `demo`.

   [CA1032: Implementujte standardní konstruktory](../code-quality/ca1032-implement-standard-exception-constructors.md)výjimky: Microsoft.Design: Do této třídy přidejte následující konstruktor: protected demo (SerializationInfo, StreamingContext)

   1. Přidejte kód `using System.Runtime.Serialization;` na začátek souboru Class1.cs.

   1. Dále přidejte konstruktor`protected demo (SerializationInfo info, StreamingContext context) : base(info, context) { } to the class demo.`

   [CA1032: Implementujte standardní konstruktory](../code-quality/ca1032-implement-standard-exception-constructors.md)výjimky: Microsoft.Design: Do této třídy přidejte následující konstruktor: public demo ()

   1. Přidejte konstruktor `public demo () : base() { }` do třídy **.** `demo`

   [CA1709: Identifikátory by se měly použita](../code-quality/ca1709-identifiers-should-be-cased-correctly.md)správně: Microsoft. pojmenování: Opravte použití malých a velkých písmen názvu oboru názvů ' testCode ', a to změnou na ' TestCode '.

   1. Změňte velikost písmen oboru názvů `testCode` na. `TestCode`

   [CA1709: Identifikátory by se měly použita](../code-quality/ca1709-identifiers-should-be-cased-correctly.md)správně: Microsoft. pojmenování: Opravte použití malých a velkých písmen typu "demo", a to změnou na demo.

   1. Změňte název člena na `Demo`.

   [CA1709: Identifikátory by se měly použita](../code-quality/ca1709-identifiers-should-be-cased-correctly.md)správně: Microsoft. pojmenování: Opravte použití malých a velkých písmen názvu člena ' Item ' změnou na ' Item '.

   1. Změňte název člena na `Item`.

   [CA1710: Identifikátory by měly mít správnou](../code-quality/ca1710-identifiers-should-have-correct-suffix.md)příponu: Microsoft. pojmenování: Přejmenujte ' testCode. Demo ' na konec ' Exception '.

   1. Změňte název třídy a jejích konstruktorů na `DemoException`.

   [CA2210: Sestavení by měly mít platné silné](../code-quality/ca2210-assemblies-should-have-valid-strong-names.md)názvy: Podepište ' CodeAnalysisManagedDemo ' pomocí klíče silného názvu.

   1. V nabídce **projekt** vyberte **vlastnosti CodeAnalysisManagedDemo**.

      Zobrazí se vlastnosti projektu.

   1. Klikněte na kartu **podepisování** .

   1. Zaškrtněte políčko **podepsat sestavení** .

   1. V seznamu **Vyberte soubor klíče s názvem řetězce** vyberte možnost  **\<nový... >** .

      Zobrazí se dialogové okno **vytvořit klíč se silným názvem** .

   1. Do pole **název souboru klíče**zadejte TestKey.

   1. Zadejte heslo a klikněte na **tlačítko OK**.

   1. V nabídce **soubor** klikněte na příkaz **Uložit vybrané položky**a poté zavřete stránky vlastností.

   [CA2237: Označte typy ISerializable pomocí SerializableAttribute](../code-quality/ca2237-mark-iserializable-types-with-serializableattribute.md): Microsoft. Usage: Přidejte atribut [serializovatelný] do typu demo, protože tento typ implementuje ISerializable.

   1. Přidejte atribut do třídy `demo`. `[Serializable ()]`

   Až změny dokončíte, soubor Class1.cs by měl vypadat takto:

   ```csharp
   using System;
   using System.Runtime.Serialization;

   namespace TestCode
   {
       [Serializable()]
       public class DemoException : Exception
       {
           public DemoException () : base() { }
           public DemoException(String s) : base(s) { }
           public DemoException(String s, Exception e) : base(s, e) { }
           protected DemoException(SerializationInfo info, StreamingContext context) : base(info, context) { }

           public static void Initialize(int size) { }
           protected static readonly int _item;
           public static int Item { get { return _item; } }
       }
   }
   ```

1. Znovu sestavte projekt.

## <a name="exclude-code-analysis-warnings"></a>Upozornění analýzy kódu vyloučení

1. Pro každé ze zbývajících upozornění proveďte následující:

    1. Vyberte upozornění v **Seznam chyb**.

    1. V nabídce kliknutím pravým tlačítkem (kontextová nabídka) vyberte **potlačit** > **v souboru potlačení**.

1. Znovu sestavte projekt.

     Projekt se vytváří bez upozornění a chyb.

## <a name="see-also"></a>Viz také:

[Analýza kódu pro spravovaný kód](../code-quality/code-analysis-for-managed-code-overview.md)