---
title: Názorný postup analýza spravovaného kódu na výskyt závad kódu | Dokumentace Microsoftu
ms.date: 01/29/2018
ms.topic: conceptual
helpviewer_keywords:
- code analysis [Visual Studio]
- managed code, analyzing
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: 93bd0fd71fbe8eae90750aa2e7597ee40bba17a2
ms.sourcegitcommit: 5483e399f14fb01f528b3b194474778fd6f59fa6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/05/2019
ms.locfileid: "66715272"
---
# <a name="walkthrough-analyzing-managed-code-for-code-defects"></a>Návod: Analýza defektů spravovaného kódu

V tomto podrobném návodu analyzujete spravovaný projekt závad v kódu pomocí nástroje Analýza kódu.

Tento názorný postup vás provede procesem pomocí analýzy kódu pro analýzu sestavení .NET spravovat kód pro soulad s pokyny k návrhu rozhraní .NET.

## <a name="create-a-class-library"></a>Vytvoření knihovny tříd

### <a name="to-create-a-class-library"></a>Chcete-li vytvořit knihovnu tříd

1. Na **souboru** nabídce zvolte **nový** > **projektu**.

1. V **nový projekt** dialogového okna rozbalte **nainstalováno** > **Visual C#** a klikněte na tlačítko **Windows Desktop**.

1. Zvolte **knihovna tříd (.NET Framework)** šablony.

1. V **název** textového pole, typ **CodeAnalysisManagedDemo** a potom klikněte na tlačítko **OK**.

1. Po vytvoření projektu, otevřete *Class1.cs* souboru.

1. Nahraďte existující text v Class1.cs následujícím kódem:

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

## <a name="analyze-the-project"></a>Analýza projektu

### <a name="to-analyze-a-managed-project-for-code-defects"></a>K analýze spravovaných projektů závad v kódu

1. Vyberte projekt CodeAnalysisManagedDemo v **Průzkumníka řešení**.

1. Na **projektu** nabídky, klikněte na tlačítko **vlastnosti**.

     Zobrazí se stránka Vlastnosti CodeAnalysisManagedDemo.

1. Zvolte **analýzy kódu** kartu.

1. Ujistěte se, že **povolit analýzu kódu na sestavení** je zaškrtnuté políčko.

1. Z **spustit tuto sadu pravidel** rozevíracího seznamu vyberte **všechna pravidla společnosti Microsoft**.

1. Na **souboru** nabídky, klikněte na tlačítko **uložit vybrané položky**a pak zavřete vlastnosti stránky.

1. Na **sestavení** nabídky, klikněte na tlačítko **sestavení CodeAnalysisManagedDemo**.

    Upozornění sestavení projektu CodeAnalysisManagedDemo jsou uvedeny v **seznam chyb** a **výstup** systému windows.

## <a name="correct-the-code-analysis-issues"></a>Opravte problémy s analýzou kódu

### <a name="to-correct-code-analysis-rule-violations"></a>Chcete-li opravit porušení pravidel analýzy kódu

1. Na **zobrazení** nabídce zvolte **seznam chyb**.

    V závislosti na profil pro vývojáře, který jste zvolili, možná budete muset odkazovat na **ostatní Windows** na **zobrazení** nabídky a klikněte na tlačítko **seznam chyb**.

1. V **Průzkumníka řešení**, zvolte **zobrazit všechny soubory**.

1. Rozbalte uzel vlastnosti a pak otevřete *AssemblyInfo.cs* souboru.

1. Chcete-li opravit upozornění použijte následující tipy:

   [CA1014: Označte sestavení pomocí atributu CLSCompliantAttribute](../code-quality/ca1014-mark-assemblies-with-clscompliantattribute.md): Microsoft.Design: 'ukázka' by měla být označena pomocí CLSCompliantAttribute a jeho hodnota by měla mít hodnotu true.

   1. Přidejte kód `using System;` soubor AssemblyInfo.cs.

   1. V dalším kroku přidejte kód `[assembly: CLSCompliant(true)]` na konec souboru AssemblyInfo.cs.

   [CA1032: Implementujte standardní konstruktory výjimky](../code-quality/ca1032-implement-standard-exception-constructors.md): Microsoft.Design: Přidejte následující konstruktor k této třídě: veřejné demo(String)

   1. Přidejte konstruktor `public demo (String s) : base(s) { }` do třídy `demo`.

   [CA1032: Implementujte standardní konstruktory výjimky](../code-quality/ca1032-implement-standard-exception-constructors.md): Microsoft.Design: Přidejte následující konstruktor k této třídě: veřejné ukázkové (String, výjimka)

   1. Přidejte konstruktor `public demo (String s, Exception e) : base(s, e) { }` do třídy `demo`.

   [CA1032: Implementujte standardní konstruktory výjimky](../code-quality/ca1032-implement-standard-exception-constructors.md): Microsoft.Design: Přidejte následující konstruktor k této třídě: chráněné ukázka (SerializationInfo, StreamingContext)

   1. Přidejte kód `using System.Runtime.Serialization;` na začátek souboru Class1.cs.

   1. V dalším kroku přidejte konstruktor `protected demo (SerializationInfo info, StreamingContext context) : base(info, context) { } to the class demo.`

   [CA1032: Implementujte standardní konstruktory výjimky](../code-quality/ca1032-implement-standard-exception-constructors.md): Microsoft.Design: Přidejte následující konstruktor k této třídě: veřejné demo()

   1. Přidejte konstruktor `public demo () : base() { }` do třídy `demo` **.**

   [CA1709: Identifikátory by měly být správně formátováno](../code-quality/ca1709-identifiers-should-be-cased-correctly.md): Microsoft.Naming: Opravte použití malých a velkých oboru názvů názvu 'testCode' pomocí změny na "TestCode".

   1. Změna velikosti písmen názvů `testCode` k `TestCode`.

   [CA1709: Identifikátory by měly být správně formátováno](../code-quality/ca1709-identifiers-should-be-cased-correctly.md): Microsoft.Naming: Opravte použití malých a velkých název typu 'ukázku"změnou"Ukázka".

   1. Název členu, který chcete změnit `Demo`.

   [CA1709: Identifikátory by měly být správně formátováno](../code-quality/ca1709-identifiers-should-be-cased-correctly.md): Microsoft.Naming: Opravte použití malých a velkých název člena 'item' pomocí změny na "Položka".

   1. Název členu, který chcete změnit `Item`.

   [CA1710: Identifikátory by měly mít správnou příponu](../code-quality/ca1710-identifiers-should-have-correct-suffix.md): Microsoft.Naming: Přejmenujte "testCode.demo" za účelem v 'Exception'.

   1. Změnit název třídy a jejích konstruktorů k `DemoException`.

   [CA2210: Sestavení by měly mít platné silné názvy](../code-quality/ca2210-assemblies-should-have-valid-strong-names.md): "CodeAnalysisManagedDemo" podepište klíče silného názvu.

   1. Na **projektu** nabídce zvolte **CodeAnalysisManagedDemo vlastnosti**.

      Zobrazí vlastnosti projektu.

   1. Zvolte **podepisování** kartu.

   1. Vyberte **podepsat sestavení** zaškrtávací políčko.

   1. V **vybrat soubor klíče název řetězce** seznamu vyberte  **\<nový … >** .

      **Vytvořit klíč se silným názvem** zobrazí se dialogové okno.

   1. V **název souboru klíče**, zadejte TestKey.

   1. Zadejte heslo a klikněte na tlačítko **OK**.

   1. Na **souboru** nabídce zvolte **uložit vybrané položky**a pak zavřete stránku vlastností.

   [CA2237: Označte typy ISerializable pomocí SerializableAttribute](../code-quality/ca2237-mark-iserializable-types-with-serializableattribute.md): Microsoft.Usage: Přidejte atribut [Serializable] na typ 'ukázka' protože tento typ implementuje ISerializable.

   1. Přidat `[Serializable ()]` atribut třídy `demo`.

   Po dokončení změny souboru Class1.cs by měl vypadat nějak takto:

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

1. Sestavte projekt znovu.

## <a name="exclude-code-analysis-warnings"></a>Vyloučit upozornění analýzy kódu

1. Pro každý zbývající upozornění postupujte takto:

    1. Výběr varování v **seznam chyb**.

    1. V místní nabídce (kontextová nabídka), zvolte **potlačit** > **v souboru potlačení**.

1. Sestavte projekt znovu.

     Projekt se sestaví bez žádná upozornění ani chyby.

## <a name="see-also"></a>Viz také:

[Analýza kódu pro spravovaný kód](../code-quality/code-analysis-for-managed-code-overview.md)