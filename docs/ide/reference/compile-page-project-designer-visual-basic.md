---
title: "Stránka kompilovat, Návrhář (Visual Basic) projektu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vb.ProjectPropertiesCompile
helpviewer_keywords:
- compilation, Visual Basic projects
- compilation, options [Visual Basic]
- compilers, Visual Basic options
- compilation, instructions [Visual Basic]
- compiler options, Visual Basic
- Project Designer, Compile page
- Compile page in Project Designer
ms.assetid: b2a80230-906e-4e85-b3e0-fcd9c40426e1
caps.latest.revision: "60"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 23289047783eefb6c4ebe3c29b9e372cd5aae695
ms.sourcegitcommit: c0422a3d594ea5ae8fc03f1aee684b04f417522e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/02/2017
---
# <a name="compile-page-project-designer-visual-basic"></a>Stránka Kompilovat, návrhář projektu (Visual Basic)
Použití **zkompilovat** stránky v Návrháři projektu k určení kompilace pokyny. Na této stránce můžete také zadat kompilátoru pokročilé možnosti a před sestavením nebo po sestavení událostí.  
  
Pro přístup k **zkompilovat** vyberte uzel projektu (ne **řešení** uzel) v **Průzkumníku řešení**. Zvolte **projektu**, **vlastnosti** v řádku nabídek. Jakmile se zobrazí v Návrháři projektu, klikněte na tlačítko **zkompilovat** kartě.  
  
[!INCLUDE[note_settings_general](../../data-tools/includes/note_settings_general_md.md)]  
  
## <a name="configuration-and-platform"></a>Konfigurace a platformy  
 Následující nastavení umožňuje vybrat konfigurace a platformy můžete zobrazit nebo upravit.  
  
> [!NOTE]
>  S konfigurací zjednodušené sestavení projektu systému určuje, zda sestavování ladění a vydání verze. Proto **konfigurace** a **platformy** seznamy nejsou zobrazeny. Další informace najdete v tématu [ladění a vydání konfigurace projektu](http://msdn.microsoft.com/en-us/0440b300-0614-4511-901a-105b771b236e).  
  
 **Konfigurace**  
 Určuje nastavení konfigurace, které chcete zobrazit nebo změnit. Nastavení jsou **ladění** (výchozí), **verze**, nebo **všechny konfigurace**. Další informace najdete v tématu [ladění a vydání konfigurace projektu](http://msdn.microsoft.com/en-us/0440b300-0614-4511-901a-105b771b236e) a [postupy: vytvoření a úprava konfigurací](../../ide/how-to-create-and-edit-configurations.md).  
  
 **Platforma**  
 Určuje nastavení platformy, které chcete zobrazit nebo změnit. Můžete zadat **libovolný procesor** (výchozí), **x64**, nebo **x86**. Další informace najdete v tématu [ladění a vydání konfigurace projektu](http://msdn.microsoft.com/en-us/0440b300-0614-4511-901a-105b771b236e).  
  
## <a name="compiler-configuration-options"></a>Možnosti konfigurace kompilátoru  
 Tato nastavení umožňují nastavit kompilátor možnosti konfigurace.  
  
 **Vytvoření výstupní cesta**  
 Určuje umístění výstupních souborů pro tento projekt konfiguraci. Zadejte cestu k výstupu sestavení v tomto poli, nebo klikněte **Procházet** tlačítko vyberte cestu. Všimněte si, že cesta je relativní; Pokud chcete zadat absolutní cestu, bude uložen jako relativní. Výchozí cesta je bin\Debug\ nebo bin\Release\\. Další informace najdete v tématu [ladění a vydání konfigurace projektu](http://msdn.microsoft.com/en-us/0440b300-0614-4511-901a-105b771b236e).  
  
 S konfigurací zjednodušené sestavení projektu systému určuje, zda sestavování ladění a vydání verze. **Sestavení** příkaz **ladění** nabídky (F5) bude umístěte sestavení do umístění ladění, bez ohledu na to **výstupní cesta** zadáte. Ale **sestavení** příkaz **sestavení** nabídky vloží ho do umístění, které zadáte. Další informace najdete v tématu [ladění a vydání konfigurace projektu](http://msdn.microsoft.com/en-us/0440b300-0614-4511-901a-105b771b236e).  
  
 **Možnost explicitní**  
 Určuje, jestli se má povolit implicitní deklarace proměnných. Vyberte **na** tak, aby vyžadovala explicitní deklarace proměnné. To způsobí, že kompilátoru zprávy o chybách Pokud proměnné nejsou deklarovat, než se používají. Vyberte **vypnout** umožňuje implicitní deklarace proměnných.  
  
 Toto nastavení odpovídá [/optionexplicit](/dotnet/visual-basic/reference/command-line-compiler/optionexplicit) – možnost kompilátoru.  
  
 Pokud obsahuje souboru zdrojového kódu [Option Explicit – příkaz](/dotnet/visual-basic/language-reference/statements/option-explicit-statement), `On` nebo `Off` hodnota v příkazu přepíše **Option Explicit** nastavení na **kompilace stránka**.  
  
 Když vytvoříte nový projekt, **Option Explicit** nastavení na **kompilace stránky** je nastaven na hodnotu **Option Explicit** nastavení v **možnosti**  dialogové okno. Zobrazení nebo změna nastavení v tomto dialogovém na **nástroje** nabídky, klikněte na tlačítko **možnosti**. V **možnosti** dialogové okno, rozbalte seznam **projekty a řešení**a potom klikněte na **VB výchozí**. Počáteční výchozí nastavení **Option Explicit** v **VB výchozí** je **na**.  
  
 Nastavení **Option Explicit** k `Off` je obecně není vhodné. Může chybně název proměnné v jedné nebo více umístění, což by způsobilo neočekávané výsledky při spuštění programu.  
  
 **Možnost striktní**  
Určuje, jestli se k vynucení sémantika striktní typu. Když **možnost striktní** je **na**, způsobit chybu kompilace následující podmínky:  
  
-   Implicitní zužující převody  
  
-   Pozdní vazba  
  
-   Implicitní zadáte, která způsobí, že `Object` typu  
  
Implicitní zužující převod chyby nastane, když je převod typu implicitní data, která je zužující převod. Další informace najdete v tématu [Option Strict – příkaz](/dotnet/visual-basic/language-reference/statements/option-strict-statement), [implicitní a explicitní převody](/dotnet/visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions), a [Widening a zužující převody](/dotnet/visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions).  
  
Objekt je pozdní vazba, když je přiřazen k vlastnosti nebo metody proměnné, která je deklarován jako typ `Object`. Další informace najdete v tématu [Option Strict – příkaz](/dotnet/visual-basic/language-reference/statements/option-strict-statement) a [Early a pozdní vazby](/dotnet/visual-basic/programming-guide/language-features/early-late-binding/early-and-late-binding).  
  
Dochází k chybám typu implicitní objekt když příslušného typu nelze odvodit deklarované proměnné, takže typ `Object` je odvodit. Především proběhne, když používáte `Dim` příkaz deklarovat proměnnou bez použití `As` klauzuli a `Option Infer` je vypnutý. Další informace najdete v tématu [Option Strict – příkaz](/dotnet/visual-basic/language-reference/statements/option-strict-statement), [Option Infer – příkaz](/dotnet/visual-basic/language-reference/statements/option-infer-statement)a [specifikace jazyka Visual Basic](/dotnet/visual-basic/reference/language-specification).  
  
**Možnost striktní** nastavení odpovídá [/optionstrict](/dotnet/visual-basic/reference/command-line-compiler/optionstrict) – možnost kompilátoru.  
  
Pokud zdrojový soubor obsahuje [Option Strict – příkaz](/dotnet/visual-basic/language-reference/statements/option-strict-statement), `On` nebo `Off` hodnota v příkazu přepíše **možnost striktní** nastavení na **kompilace stránky** .  
  
Při vytváření projektu, **možnost striktní** nastavení na **kompilace stránky** je nastaven na hodnotu **možnost striktní** nastavení v **možnosti** dialogové okno. Zobrazení nebo změna nastavení v tomto dialogovém na **nástroje** nabídky, klikněte na tlačítko **možnosti**. V **možnosti** dialogové okno, rozbalte seznam **projekty a řešení**a potom klikněte na **VB výchozí**. Počáteční výchozí nastavení **možnost striktní** v **VB výchozí** je **vypnout**.  
  
**Možnost striktní jednotlivých upozornění.** **Upozornění konfigurace** části **kompilace stránky** má nastavení, které odpovídají tři podmínky, které způsobí chybu kompilace při `Option Strict` na. Tato nastavení jsou následující:  
  
-   **Implicitní převod**  
  
-   **Pozdní vazba; volání by mohlo selhat v době běhu**  
  
-   **Implicitní typ; předpokládá, že objekt**  
  
Když nastavíte **možnost striktní** k **na**, všechny tři z těchto nastavení upozornění konfigurace jsou nastaveny na **chyba**. Když nastavíte **možnost striktní** k **vypnout**, všechny tři nastavení **žádné**.  
  
Jednotlivě můžete změnit nastavení každou upozornění konfigurace **žádné**, **upozornění**, nebo **chyba**. Pokud mají všechny tři nastavení konfigurace upozornění **chyba**, `On` se zobrazí v `Option strict` pole. Pokud mají všechny tři **žádné**, `Off` se zobrazí v tomto poli. Pro libovolnou kombinací těchto nastavení **(vlastní)** se zobrazí.  
  
**Možnost porovnání**  
Určuje typ porovnání řetězců používat. Vyberte **binární** kompilátoru použít porovnávání řetězců binární, malá a velká písmena. Vyberte **Text** použít porovnávání řetězců text národního prostředí, která se velká a malá písmena.  
  
Toto nastavení odpovídá [/optioncompare](/dotnet/visual-basic/reference/command-line-compiler/optioncompare) – možnost kompilátoru.  
  
Pokud obsahuje souboru zdrojového kódu [Option Compare – příkaz](/dotnet/visual-basic/language-reference/statements/option-compare-statement), `Binary` nebo `Text` hodnota v příkazu přepíše **možnost porovnat** nastavení na **kompilace stránka**.  
  
Při vytváření projektu, **možnost porovnat** nastavení na **kompilace stránky** je nastaven na hodnotu **možnost porovnat** nastavení v **možnosti** dialogové okno. Zobrazení nebo změna nastavení v tomto dialogovém na **nástroje** nabídky, klikněte na tlačítko **možnosti**. V **možnosti** dialogové okno, rozbalte seznam **projekty a řešení**a potom klikněte na **VB výchozí**. Počáteční výchozí nastavení **možnost porovnat** v **VB výchozí** je **binární**.  
  
**Option infer –**  
Určuje, jestli se tak, aby měl odvození místního typu deklarace proměnných. Vyberte **na** k povolení použití odvození místního typu. Vyberte **vypnout** k odvození místního typu bloku.  
  
Toto nastavení odpovídá [/optioninfer](/dotnet/visual-basic/reference/command-line-compiler/optioninfer) – možnost kompilátoru.  
  
Pokud zdrojový soubor obsahuje [Option Infer – příkaz](/dotnet/visual-basic/language-reference/statements/option-infer-statement), `On` nebo `Off` hodnota v příkazu přepíše **Option Infer –** nastavení na **kompilace stránky** .  
  
Při vytváření projektu, **Option Infer –** nastavení na **kompilace stránky** je nastaven na hodnotu **Option Infer –** nastavení v **možnosti**dialogové okno. Zobrazení nebo změna nastavení v tomto dialogovém na **nástroje** nabídky, klikněte na tlačítko **možnosti**. V **možnosti** dialogové okno, rozbalte seznam **projekty a řešení**a potom klikněte na **VB výchozí**. Počáteční výchozí nastavení **Option Infer –** v **VB výchozí** je **na**.  
  
**Cíl procesoru**  
Určuje procesoru, které se zaměřují výstupní soubor. Zadejte **x86** pro jakýkoli 32-bit Intel kompatibilní procesor, **x64** pro všechny 64bitový procesor Intel kompatibilní, **ARM** pro jakýkoli procesor ARM nebo **libovolný procesor**  k určení, že jakýkoli procesor je přijatelná. **Všechny procesoru** je výchozí hodnota pro nové projekty, protože umožňuje aplikaci, aby běžela na největší počet typy hardwaru.  
  
Další informace najdete v tématu [/Platform (Visual Basic)](/dotnet/visual-basic/reference/command-line-compiler/platform).  
  
**Dáváte přednost 32-bit**  
Pokud **Prefer32 bitů** je zaškrtnuté políčko, je aplikace spuštěná jako 32bitová aplikace na 32bitové a 64bitové verze systému Windows. Jinak je aplikace spuštěná jako 32bitová aplikace na 32bitové verze systému Windows a jako 64bitové aplikaci v 64bitových verzích systému Windows.  
  
Spuštění jako 64bitové aplikaci zdvojnásobuje velikost ukazatele a může to způsobit problémy s kompatibilitou s knihovny, které jsou výhradně 32-bit. Má smysl pouze v případě, že výrazně rychleji spustí nebo potřebuje více než 4 GB paměti spuštění aplikace jako 64-bit.  
  
Toto zaškrtávací políčko je dostupné jenom v případě, že jsou splněny všechny následující podmínky:  
  
-   Na **stránka kompilovat**, **cílový procesor** seznamu je nastavena na **libovolný procesor**.  
  
-   Na **stránky aplikace**, **typ aplikace** seznamu určuje, že je projekt aplikace.  
  
-   Na **stránky aplikace**, **cílové rozhraní** seznamu určuje rozhraní .NET Framework 4.5.  
  
**Upozornění konfigurace**  
Tato tabulka uvádí podmínky sestavení a odpovídající úroveň oznámení **žádné**, **upozornění**, nebo **chyba** pro každou.  
  
Ve výchozím nastavení všechna upozornění kompilátoru se přidají do seznamu úkolů během kompilace. Vyberte **zakázat všech upozornění** kompilátoru nechcete problém varování nebo chyby. Vyberte **zpracovává všechna upozornění jako chyby** Pokud chcete, aby kompilátoru, aby považoval upozornění jako chyby, které musí být vyřešeny.  
  
**Zakáže všechna upozornění**  
Určuje, jestli se pro povolení oznámení problému uvedeného v kompilátoru **podmínku a oznámení** tabulky popsané dříve v tomto dokumentu. Ve výchozím nastavení je toto políčko zaškrtnuté. Výběrem tohoto zaškrtávacího políčka kompilátoru není vydat varování nebo chyby.  
  
Toto nastavení odpovídá [/nowarn](/dotnet/visual-basic/reference/command-line-compiler/nowarn) – možnost kompilátoru.  
  
**Zpracovává všechna upozornění jako chyby**  
Určuje, jak zacházet s upozorněními. Ve výchozím nastavení, tato zaškrtnutí políčka, takže všechna oznámení upozornění zůstanou nastavena **upozornění**. Toto políčko zaškrtněte, chcete-li změnit všechna oznámení upozornění na **chyba**.  
  
Tato možnost je dostupná pouze v případě **zakázat všech upozornění** se vymaže.  
  
**Generování souborů dokumentace XML**  
Určuje, zda chcete vygenerovat dokumentaci informace. Ve výchozím nastavení toto zaškrtávací políčko zaškrtnuto, instruující kompilátoru generovat informace o dokumentaci a její zahrnutí do souboru XML. Zrušte zaškrtnutí tohoto políčka kompilátoru nevytvářet dokumentaci.  
  
Toto nastavení odpovídá [/doc](/dotnet/visual-basic/reference/command-line-compiler/doc) – možnost kompilátoru.  
  
**Registrace pro zprostředkovatel komunikace s objekty COM**  
Určuje, zda se ve spravované aplikaci vystavovat objektu COM (Obálka volatelná aplikacemi COM), která umožňuje objektu COM k interakci s aplikací.  
  
Ve výchozím nastavení je toto políčko zaškrtnuté, která určuje, že aplikace nebude povolovat zprostředkovatel komunikace s objekty COM. Výběrem tohoto zaškrtávacího políčka Povolit zprostředkovatel komunikace s objekty COM.  
  
Tato možnost není k dispozici pro aplikaci systému Windows nebo aplikace konzoly projekty.  
  
**Události sestavení**  
Kliknutím na toto tlačítko přístup **události sestavení** dialogové okno. Pomocí tohoto dialogového okna zadejte pokyny ke konfiguraci před a po sestavení pro projekt. Toto dialogové okno se vztahují na projekty Visual Basic jenom. Další informace najdete v tématu [sestavení dialogové okno události (Visual Basic)](../../ide/reference/build-events-dialog-box-visual-basic.md).  
  
**Možnosti rozšířené kompilace**  
Kliknutím na toto tlačítko přístup **AdvancedCompiler nastavení** dialogové okno. Použití **AdvancedCompiler nastavení** dialogové okno zadat projektu rozšířenou vlastností konfigurace sestavení. Toto dialogové okno se vztahují na projekty Visual Basic jenom. Další informace najdete v tématu [Advanced kompilátoru dialogové okno nastavení (Visual Basic)](../../ide/reference/advanced-compiler-settings-dialog-box-visual-basic.md).  
  
## <a name="see-also"></a>Viz také  
 [Konfigurace ladění a verzí projektu](http://msdn.microsoft.com/en-us/0440b300-0614-4511-901a-105b771b236e)   
 [Správa vlastností kompilace](http://msdn.microsoft.com/en-us/94308881-f10f-4caf-a729-f1028e596a2c)   
 [Postupy: určení událostí sestavení (Visual Basic)](../../ide/how-to-specify-build-events-visual-basic.md)   
 [Visual Basic – kompilátor příkazového řádku](/dotnet/visual-basic/reference/command-line-compiler/index)   
 [Postupy: vytvoření a úprava konfigurací](../../ide/how-to-create-and-edit-configurations.md)