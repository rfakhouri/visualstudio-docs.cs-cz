---
title: "Návod: Analýza spravovaného kódu na výskyt závad kódu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- code analysis, walkthroughs
- managed code, analyzing
- code analysis tool, walkthroughs
ms.assetid: 22b99f49-1924-4fb5-a421-c8b23e5d5cd4
caps.latest.revision: "45"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: dotnet
ms.openlocfilehash: 6ea39704ea232fb304257b897087f0ae60d19c4f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-analyzing-managed-code-for-code-defects"></a>Návod: Analýza spravovaného kódu na výskyt závad v kódu
V tomto návodu analyzovat spravovaný projekt pro defekty kódu pomocí nástroje Analýza kódu.  
  
 Tento návod vám projděte proces pomocí analýzy kódu pro analýzu sestavení kódu vaší spravované rozhraní .NET pro shodu s pokyny návrhu rozhraní Microsoft .NET Framework.  
  
 V tomto návodu můžete:  
  
-   Analýza a opravte upozornění vadou kódu.  
  
## <a name="prerequisites"></a>Požadavky  
  
-   [!INCLUDE[vsPreLong](../code-quality/includes/vsprelong_md.md)].  
  
## <a name="create-a-class-library"></a>Vytvoření knihovny tříd  
  
#### <a name="to-create-a-class-library"></a>K vytvoření knihovny tříd  
  
1.  Na **soubor** nabídky [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)], klikněte na tlačítko **nový** a pak klikněte na **projektu**.  
  
2.  V **nový projekt** dialogovém **typy projektů**, klikněte na tlačítko **Visual C#**.  
  
3.  V části **šablony**, vyberte **knihovny tříd**.  
  
4.  V **název** textového pole, typ **CodeAnalysisManagedDemo** a pak klikněte na **OK**.  
  
5.  Po vytvoření projektu otevřete soubor Class1.cs.  
  
6.  Nahradí existující text v Class1.cs následujícím kódem:  
  
     `//CodeAnalysisManagedDemo //Class1.cs using System;  namespace testCode {          public class demo : Exception     {                  public static void Initialize(int size) { }         protected static readonly int _item;         public static int item { get { return _item; } }     } }`  
  
7.  Uložte soubor Class1.cs.  
  
## <a name="analyze-the-project"></a>Analýza projektu  
  
#### <a name="to-analyze-a-managed-project-for-code-defects"></a>K analýze spravovaný projekt pro defekty kódu  
  
1.  Vyberte projekt CodeAnalysisManagedDemo v **Průzkumníku řešení**.  
  
2.  Na **projektu** nabídky, klikněte na tlačítko **vlastnosti**.  
  
     Zobrazí se stránka vlastností CodeAnalysisManagedDemo.  
  
3.  Klikněte na tlačítko **CodeAnalysis**.  
  
4.  Ujistěte se, že **povolit analýza kódu v sestavení (definuje CODE_ANALYSIS konstanta**) je zaškrtnuté.  
  
5.  Z **spuštění této sady pravidel** rozevíracího seznamu vyberte **všechna pravidla Microsoft**.  
  
6.  Na **soubor** nabídky, klikněte na tlačítko **uložit vybrané položky**a pak zavřete ManagedDemo vlastnosti stránky.  
  
7.  Na **sestavení** nabídky, klikněte na tlačítko **sestavení ManagedDemo**.  
  
     Upozornění sestavení projektu CodeAnalysisManagedDemo oznámí **analýza kódu** a **výstup** systému windows.  
  
     Pokud **analýza kódu** nezobrazí okno, na **analyzovat** nabídce zvolte **Windows** a potom **Zvolte Analýza kódu**.  
  
## <a name="correct-the-code-analysis-issues"></a>Opravte problémy analýzy kódu  
  
#### <a name="to-correct-code-analysis-rule-violations"></a>Chcete-li opravit porušení pravidel analýzy kódu  
  
1.  Na **zobrazení** nabídky, klikněte na tlačítko **seznam chyb**.  
  
     V závislosti na vývojáře profil, který jste zvolili, možná budete muset přejděte na příkaz **ostatní okna** na **zobrazení** nabídce a pak klikněte na tlačítko **seznam chyb**.  
  
2.  V **Průzkumníku řešení**, klikněte na tlačítko **zobrazit všechny soubory**.  
  
3.  Potom rozbalte uzel vlastnosti a pak otevřete soubor AssemblyInfo.cs.  
  
4.  Opravte upozornění pomocí následující:  
  
-   [CA1014: Označte sestavení pomocí atributu CLSCompliantAttribute](../code-quality/ca1014-mark-assemblies-with-clscompliantattribute.md): Microsoft.Design: 'ukázku' by měl být označen s CLSCompliantAttribute a by měl mít hodnotu true.  
  
    -   Přidejte kód `using``System;` AssemblyInfo.cs souboru.  
  
         Dál přidejte kód `[assembly: CLSCompliant(true)]` na konec souboru AssemblyInfo.cs.  
  
         Znovu sestavte projekt.  
  
-   [CA1032: Implementujte standardní konstruktory výjimky](../code-quality/ca1032-implement-standard-exception-constructors.md): Microsoft.Design: přidejte následující konstruktor do této třídy: veřejné demo(String)  
  
    -   Přidat konstruktoru `public demo (String s) : base(s) { }` k třídě `demo`.  
  
-   [CA1032: Implementujte standardní konstruktory výjimky](../code-quality/ca1032-implement-standard-exception-constructors.md): Microsoft.Design: přidejte následující konstruktor do této třídy: veřejné ukázku (řetězec, výjimka)  
  
    -   Přidat konstruktoru `public demo (String s, Exception e) : base(s, e) { }` k třídě `demo`.  
  
-   [CA1032: Implementujte standardní konstruktory výjimky](../code-quality/ca1032-implement-standard-exception-constructors.md): Microsoft.Design: přidejte následující konstruktor do této třídy: chráněný ukázku (položku SerializationInfo, StreamingContext)  
  
    -   Přidejte kód `using System.Runtime.Serialization;` na začátek souboru Class1.cs.  
  
         Dál přidejte konstruktor`protected demo (SerializationInfo info, StreamingContext context) : base(info, context) { } to the class demo.`  
  
         Znovu sestavte projekt.  
  
-   [CA1032: Implementujte standardní konstruktory výjimky](../code-quality/ca1032-implement-standard-exception-constructors.md): Microsoft.Design: přidejte následující konstruktor do této třídy: veřejné demo()  
  
    -   Přidat konstruktoru `public demo () : base() { }` k třídě `demo` **.**  
  
         Znovu sestavte projekt.  
  
-   [CA1709: Identifikátory by měla být použita správně](../code-quality/ca1709-identifiers-should-be-cased-correctly.md): Microsoft.Naming: Opravte malá a velká písmena název oboru názvů 'testCode' změnou 'TestCode'.  
  
    -   Změnit malá a velká písmena oboru názvů `testCode` k `TestCode`.  
  
-   [CA1709: Identifikátory by měla být použita správně](../code-quality/ca1709-identifiers-should-be-cased-correctly.md): Microsoft.Naming: Opravte malá a velká písmena název typu 'ukázku' změnou 'Ukázku'.  
  
    -   Změňte název člena na `Demo`.  
  
-   [CA1709: Identifikátory by měla být použita správně](../code-quality/ca1709-identifiers-should-be-cased-correctly.md): Microsoft.Naming: Opravte malá a velká písmena název člena 'item' změnou 'Item'.  
  
    -   Změňte název člena na `Item`.  
  
-   [CA1710: Identifikátory by měly mít správnou příponu](../code-quality/ca1710-identifiers-should-have-correct-suffix.md): Microsoft.Naming: přejmenování 'testCode.demo' končit 'Výjimka'.  
  
    -   Změnit název třídy a pro její konstruktory `DemoException`.  
  
-   [CA2210: Sestavení by měly mít platné silné názvy](../code-quality/ca2210-assemblies-should-have-valid-strong-names.md): 'ManagedDemo' podepsat složitý název klíče.  
  
    -   Na **projektu** nabídky, klikněte na tlačítko **ManagedDemo vlastnosti**.  
  
         Zobrazí vlastnosti projektu.  
  
         Klikněte na tlačítko **podepisování**.  
  
         Vyberte **podepsání sestavení** zaškrtávací políčko.  
  
         V **vyberte soubor klíče název řetězec** seznamu, vyberte  **\<nová... >**.  
  
         **Vytvořit klíč se silným názvem** zobrazí se dialogové okno.  
  
         V **název souboru klíče**, zadejte TestKey.  
  
         Zadejte heslo a pak klikněte na tlačítko **OK**.  
  
         Na **soubor** nabídky, klikněte na tlačítko **uložit vybrané položky**a pak zavřete stránky vlastností.  
  
         Znovu sestavte projekt.  
  
-   [CA2237: Označte typy ISerializable pomocí SerializableAttribute](../code-quality/ca2237-mark-iserializable-types-with-serializableattribute.md): Microsoft.Usage: přidání atributu [Serializable] na typ 'ukázku, protože tento typ implementuje vlastnost ISerializable.  
  
    -   Přidat `[Serializable ()]` atribut třídy `demo`.  
  
         Znovu sestavte projekt.  
  
 Po dokončení změny souboru Class1.cs by měl vypadat asi takto:  
  
```  
//CodeAnalysisManagedDemo  
//Class1.cs  
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
  
## <a name="exclude-code-analysis-warnings"></a>Vyloučit upozornění analýzy kódu  
  
#### <a name="to-exclude-code-defect-warnings"></a>Vyloučit upozornění vadou kódu  
  
1.  Pro každý zbývající upozornění, postupujte takto:  
  
    1.  V okně nástroje Analýza kódu vyberte upozornění.  
  
    2.  Zvolte **akce**, zvolte **potlačit zpráva**a potom zvolte **v souboru projektu potlačení**.  
  
     Další informace najdete v tématu [postupy: potlačení upozornění s použitím položky nabídky](../code-quality/how-to-suppress-warnings-by-using-the-menu-item.md)  
  
2.  Znovu sestavte projekt.  
  
     Sestavení projektu bez žádná upozornění ani chyby.