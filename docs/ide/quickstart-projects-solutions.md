---
title: Úvod do projektů a řešení v sadě Visual Studio
ms.date: 12/11/2017
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: quickstart
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 70e120d0f33e89d914e50cea48aea5944612846f
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/04/2018
ms.locfileid: "34747505"
---
# <a name="quickstart-projects-and-solutions"></a>Rychlý úvod: Projekty a řešení

V tento rychlý start 10 minut jsme budete zjistit, co znamená vytvoření řešení a projektu v sadě Visual Studio. Podíváme vlastnosti projektu a některé soubory, které může obsahovat. Také vytvoříme odkaz na druhý projekt.

Pokud jste ještě nenainstalovali Visual Studio, přejděte k [Visual Studio stáhne](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs) stránky instalaci zdarma.

> [!TIP]
> Jsme budete jako výukových cvičení porozumět koncepci projektu vytváření řešení a projektu od začátku v tento rychlý start. V obecné používání sady Visual Studio pravděpodobně použijete mnoho šablony projektů, které Visual Studio nabízí při vytváření nového projektu.

> [!NOTE]
> Vývoj aplikací v sadě Visual Studio řešení a projekty nejsou povinné. Můžete také právě otevřete složku, která obsahuje kód a spusťte kódování, sestavování a ladění. Například pokud jste klonovat úložiště GitHub, nemusí obsahovat projektů sady Visual Studio a jejich řešení. Další informace najdete v tématu [vývoj kódu v sadě Visual Studio bez projekty a řešení](../ide/develop-code-in-visual-studio-without-projects-or-solutions.md).

## <a name="solutions"></a>Řešení

Řešení jsou kontejnery, které jsou používány sadou Visual Studio pro organizaci jeden nebo více souvisejících s projekty. Když otevřete řešení v sadě Visual Studio, bude automaticky načíst všechny projekty, které obsahuje.

### <a name="create-a-solution"></a>Vytvoření řešení

Naše zkoumání začneme vytvořením prázdného řešení. Po získání vědět, Visual Studio, pravděpodobně nebude možné najít sami vytváření prázdný řešení příliš často. Když vytvoříte nový projekt v sadě Visual Studio, automaticky vytvoří řešení, které obsahují projektu, pokud existuje řešení ještě není otevřené.

1. Spuštění sady Visual Studio.

   Otevře se Visual Studio, a pravděpodobně uvidíte **– úvodní stránka** zabírají většinu nemovitosti okna.

1. Na řádku nabídek zvolte **soubor** > **nový** > **projektu**.

   **Nový projekt** otevře se dialogové okno.

1. V levém podokně rozbalte **jiné typy projektů**, zvolte **řešení sady Visual Studio**. V prostředním podokně vyberte **prázdného řešení**. Název řešení "QuickSolution", a potom vyberte **OK**.

   ![Šablona prázdného řešení](media/quickstart-projects-new-solution.png)

   **– Úvodní stránka** zavře a řešení se zobrazí v **Průzkumníku řešení** na pravé straně okna Visual Studio. Pravděpodobně budete používat **Průzkumníku řešení** často, chcete-li procházet obsah vašich projektů.

### <a name="add-a-project"></a>Přidat do projektu

Nyní Pojďme přidat naše první projekt do řešení. Jsme budete začít s prázdným projektem a položky, které je třeba, přidejte do projektu.

1. Klikněte pravým tlačítkem nebo kontextu nabídce **řešení 'QuickSolution'** v **Průzkumníku řešení**, zvolte **přidat** > **nový projekt**.

   **Přidat nový projekt** otevře se dialogové okno.

1. V levém podokně rozbalte **Visual C#** a zvolte **Windows Desktop**. Zvolte v prostředním podokně **prázdný projekt (rozhraní .NET Framework)**. Název projektu "QuickDate", a potom vyberte **OK** tlačítko.

   Projekt s názvem "QuickDate" se zobrazí pod řešení v **Průzkumníku řešení**. Aktuálně obsahuje jednoho souboru s názvem *App.config*.

   > [!NOTE]
   > Pokud nevidíte **Visual C#** v levém podokně dialogového okna, je potřeba nainstalovat **vývoj aplikací .NET** zatížení. Snadný způsob, jak to udělat je vybrat **otevřete instalační program Visual Studio** odkaz v levém dolním rohu dialogu. Po **instalační program Visual Studio** spustí, vyberte **vývoj aplikací .NET** zatížení a potom **upravit** tlačítko.

   ![Otevřete odkaz instalační program Visual Studio](media/quickstart-projects-open-installer.png)

## <a name="add-an-item-to-the-project"></a>Přidání položky do projektu

Máme prázdný projekt&mdash;přidejme souboru kódu.

1. Klikněte pravým tlačítkem nebo kontextu nabídce **QuickDate** v **Průzkumníku řešení**, zvolte **přidat** > **novou položku**.

   **Přidat novou položku** otevře se dialogové okno.

1. Rozbalte položku **Visual C# položky**, zvolte **kód**. V prostředním podokně vyberte **třída**. Název třídy "Kalendář" a potom vyberte **přidat** tlačítko.

   Soubor s názvem *Calendar.cs* se přidá do projektu. *.Cs* na konci je přípona souboru, který je na soubory kódu C#. Soubor se zobrazí v projektu visual hierarchie v **Průzkumníku**, a její obsah se otevře se v editoru.

1. Nahraďte obsah *Calendar.cs* soubor s následujícím kódem.

   ```csharp
   using System;

   namespace QuickDate
   {
       internal class Calendar
       {
           static void Main(string[] args)
           {
               DateTime now = GetCurrentDate();
               Console.WriteLine($"Today's date is {now}");
               Console.ReadLine();
           }

           internal static DateTime GetCurrentDate()
           {
               return DateTime.Now.Date;
           }
       }
   }
   ```

   Není nutné pochopit, co kód dělá, ale pokud chcete, můžete spustit program a zjistit, že vytiskne dnešní datum v okně konzoly.

## <a name="add-a-second-project"></a>Přidání druhého projektu

Je běžné pro řešení obsahovat více než jeden projekt a často tyto reference projekty navzájem. Některé projekty v řešení může být knihovny tříd, některé spustitelný soubor aplikace, a některé, mohou být projektů testování částí nebo weby.

Umožňuje přidat projektu testů jednotek pro naše řešení. Tentokrát začneme ze šablony projektu, proto nemáme soubor další kód přidejte do projektu.

1. Klikněte pravým tlačítkem nebo kontextu nabídce **řešení 'QuickSolution'** v **Průzkumníku řešení**, zvolte **přidat** > **nový projekt**.

   **Přidat nový projekt** otevře se dialogové okno.

1. V levém podokně rozbalte **jazyka Visual Basic** a zvolte **Test** kategorie. V prostředním podokně vyberte **projektu testování částí (rozhraní .NET Framework)**. Název projektu "QuickTest" a potom vyberte **OK** tlačítko.

   Druhý projekt je přidán do **Průzkumníku řešení**a soubor s názvem *UnitTest1.vb* otevře v editoru. *VB* je přípona souboru, který je na soubory s kódem jazyka Visual Basic.

   ![Průzkumník řešení se dva projekty](media/quickstart-projects-solution-explorer.png)

## <a name="add-a-project-reference"></a>Přidat odkaz na projekt

Vytvoříme k otestování naší metoda v použít nového projektu testů jednotek **QuickDate** projektu, takže je potřeba přidat odkaz na tento projekt. Tím se vytvoří závislost sestavení mezi dva projekty, což znamená **QuickDate** budou vytvořeny před **QuickTest** když je integrované řešení.

1. Vyberte **odkazy** uzel v **QuickTest** projektu a z nabídky klikněte pravým tlačítkem nebo kontextu, zvolte **přidat odkaz na**.

   ![Přidat odkaz nabídky](media/quickstart-projects-add-reference.png)

   **Správce odkazů** otevře se dialogové okno.

1. V levém podokně rozbalte **projekty** a zvolte **řešení**. V prostředním podokně, zaškrtněte políčko vedle **QuickDate**a potom zvolte **OK** tlačítko.

   Odkaz na **QuickDate** projekt je přidán.

## <a name="add-test-code"></a>Přidat testovací kód

1. Teď přidáme testovací kód do souboru kódu jazyka Visual Basic. Nahraďte obsah *UnitTest1.vb* následujícím kódem.

   ```vb
   <TestClass()> Public Class UnitTest1

       <TestMethod()> Public Sub TestGetCurrentDate()
           Assert.AreEqual(DateTime.Now.Date, QuickDate.Calendar.GetCurrentDate())
       End Sub

   End Class
   ```

   Zobrazí se zobrazí červený "vlnovkou" v části některé kódu. Jsme budete tuto chybu opravit tak, že k testovacímu projektu [přátelského sestavení](/dotnet/csharp/programming-guide/concepts/assemblies-gac/friend-assemblies) k **QuickDate** projektu.

1. Zpět v **QuickDate** projekt, otevřete *Calendar.cs* soubor, pokud ještě není otevřené a přidejte následující pomocí příkazu a <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> atribut, chcete-li vyřešit chyby v k testovacímu projektu.

   ```csharp
   using System.Runtime.CompilerServices;

   [assembly: InternalsVisibleTo("QuickTest")]
   ```

   K souboru kódu by měla vypadat takto.

   ![Kód CSharp](media/quickstart-projects-cs-code.png)

## <a name="project-properties"></a>Vlastnosti projektu

Řádek v souboru kódu C#, který obsahuje <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> atribut odkazuje na název sestavení **QuickTest** projektu. Název sestavení nemusí být vždy stejná jako název projektu. Chcete-li najít název sestavení projektu, otevřete vlastnosti projektu.

1. V **Průzkumníku řešení**, vyberte **QuickTest** projektu. V nabídce klikněte pravým tlačítkem nebo kontextu vyberte **vlastnosti**, nebo stačí stisknout klávesu **Alt**+**Enter**.

   Na stránkách vlastností projektu otevřete **aplikace** kartě. Všimněte si, že název sestavení **QuickTest** projektu, je skutečně "QuickTest". Pokud jste chtěli změnit, je to, kde by ho změnit. Potom při sestavování testovacího projektu název spustitelného souboru, výsledná změní z *QuickTest.exe* k jste zvolili.

   ![Vlastnosti projektu](media/quickstart-projects-properties.png)

1. Prozkoumání některých dalších kartách stránky vlastností projektu, například **zkompilovat** a **nastavení**. Tyto karty se liší v závislosti na typu projektu.

## <a name="next-steps"></a>Další kroky

Pokud chcete zkontrolovat, že vaše testování částí funguje, zvolte **testování** > **spustit** > **všechny testy** z řádku nabídek. Volá se okno **Průzkumníka testů** otevře a to by měl vidět **TestGetCurrentDate** testování předává.

Blahopřejeme k dokončení tento rychlý start! Potom můžete prozkoumávat některé z dalších Quickstarts pro sadu Visual Studio nebo Další informace o tom, jak [vytváření projektů a řešení](../ide/creating-solutions-and-projects.md).

## <a name="see-also"></a>Viz také:

- [Rychlý úvod: První pohled na Visual Studio IDE](../ide/quickstart-ide-orientation.md)
- [Rychlý úvod: Přizpůsobení Visual Studio IDE a editor](../ide/quickstart-personalize-the-ide.md)
- [Rychlý úvod: Kódování v editoru](../ide/quickstart-editor.md)
- [Správa vlastností projektu a řešení](../ide/managing-project-and-solution-properties.md)
- [Správa odkazů v projektu](../ide/managing-references-in-a-project.md)
- [Vývoj kódu v sadě Visual Studio bez projektů nebo řešení](../ide/develop-code-in-visual-studio-without-projects-or-solutions.md)
- [Přehled Visual Studio IDE](../ide/visual-studio-ide.md)