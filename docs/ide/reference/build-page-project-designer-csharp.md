---
title: Stránka Sestavení, návrhář projektu (C#)
ms.date: 06/20/2017
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- cs.ProjectPropertiesBuild
helpviewer_keywords:
- Build options [C#]
- Project Designer, Build page
ms.assetid: 77ff1bfc-d633-4634-ba29-9afdb6d7e362
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: b003b3f965ab4f3857e2a532ae715d99533aa8e7
ms.sourcegitcommit: 56018fb1f52f17bf35ae2ce71c50c763486e6173
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/04/2018
ms.locfileid: "33103486"
---
# <a name="build-page-project-designer-c"></a>Stránka Sestavení, návrhář projektu (C#)
Použití **sestavení** stránky **Návrhář projektu** zadat vlastnosti konfigurace sestavení projektu. Tato stránka se vztahuje na [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] pouze projekty.

Pro přístup k **sestavení** vyberte uzel projektu (ne **řešení** uzel) v **Průzkumníku řešení**. Zvolte **zobrazení**, **stránky vlastností** v nabídce. Jakmile se zobrazí v Návrháři projektu, vyberte **sestavení** kartě.

[!INCLUDE[note_settings_general](../../data-tools/includes/note_settings_general_md.md)]

## <a name="configuration-and-platform"></a>Konfigurace a platformy
Následující možnosti vám umožňuje vybrat konfigurace a platformy můžete zobrazit nebo upravit.

> [!NOTE]
> S konfigurací zjednodušené sestavení projektu systému určuje, zda sestavování ladění a vydání verze. Proto tyto možnosti nezobrazí. Další informace najdete v tématu [postupy: nastavení ladění a konfigurace verze](../../debugger/how-to-set-debug-and-release-configurations.md).

**Konfigurace** určuje nastavení konfigurace, které chcete zobrazit nebo změnit. Toto nastavení může být **aktivní (ladění)** (Toto je výchozí nastavení), **ladění**, **verze**, nebo **všechny konfigurace**.

**Platforma** určuje nastavení platformy, které chcete zobrazit nebo změnit. Ve výchozím nastavení je **aktivní (jakýkoli procesor)**. Můžete změnit pomocí active platformy **nástroje Configuration Manager**. Další informace najdete v tématu [postupy: vytvoření a úprava konfigurací](../../ide/how-to-create-and-edit-configurations.md).

## <a name="general"></a>Obecné
Následující možnosti vám umožňují konfigurovat několik nastavení kompilátoru C#.

**Podmíněná kompilace symboly** určuje symbolů, na které se má provést Podmíněná kompilace. Symboly oddělujte středníkem (";"). Další informace najdete v tématu [/ define (možnosti kompilátoru C#)](/dotnet/csharp/language-reference/compiler-options/define-compiler-option).

**Definování ladění konstanta** definuje ladění jako symbol ve zdrojovém kódu všechny soubory ve vaší aplikaci. Vyberete tuto možnost je ekvivalentní k použití `/define:DEBUG` možnost příkazového řádku.

**Definování trasování konstanta** definuje trasování jako symbol ve zdrojovém kódu všechny soubory ve vaší aplikaci. Vyberete tuto možnost je ekvivalentní k použití `/define:TRACE` možnost příkazového řádku.

**Cílová platforma** určuje procesoru, které se zaměřují výstupní soubor. Zvolte **x86** pro jakýkoli 32-bit Intel kompatibilní procesor, zvolte **x64** žádné 64bitový procesor Intel kompatibilní, zvolte **ARM** pro procesory ARM, nebo zvolte  **Všechny procesoru** k určení, že jakýkoli procesor je přijatelná. **Všechny procesoru** je výchozí hodnota pro projekty, protože umožňuje aplikaci, aby běžela na nejširší řadu hardwaru.

Další informace najdete v tématu [/Platform (možnosti kompilátoru C#)](/dotnet/csharp/language-reference/compiler-options/platform-compiler-option).

**Dáváte přednost 32-bit** Pokud **Prefer32 bitů** je zaškrtnuté políčko, je aplikace spuštěná jako 32bitová aplikace na 32bitové a 64bitové verze systému Windows. Pokud není políčko zaškrtnuto, aplikace se spouští jako 32bitová aplikace na 32bitové verze systému Windows a jako 64bitové aplikaci v 64bitových verzích systému Windows.

Pokud spouštíte aplikaci jako 64bitové aplikaci velikost zdvojnásobí ukazatele, a mohou nastat problémy s kompatibilitou u další knihovny, které jsou výhradně 32-bit. Je užitečné k 64bitové aplikaci spustit, jenom v případě, že je více než 4 GB paměti nebo 64-bit pokynů zadejte zlepšování významně zvýšit výkon.

Toto zaškrtávací políčko je dostupné jenom v případě, že jsou splněny všechny následující podmínky:

-   Na **stránku sestavení**, **Cílová platforma** seznamu je nastavena na **libovolný procesor**.

-   Na **stránky aplikace**, **výstupní typ** seznamu určuje, že je projekt aplikace.

-   Na **stránky aplikace**, **cílové rozhraní** seznamu určuje rozhraní .NET Framework 4.5.


**Povolit nezabezpečený kód** umožňuje kód, který používá [unsafe](/dotnet/csharp/language-reference/keywords/unsafe) – klíčové slovo zkompilovat. Další informace najdete v tématu [/ unsafe (možnosti kompilátoru C#)](/dotnet/csharp/language-reference/compiler-options/unsafe-compiler-option).

**Optimalizace kódu** povolit nebo zakázat optimalizace provádí kompilátoru k vytvoření výstupního souboru menší, rychlejší a efektivnější. Další informace najdete v tématu [/ optimize (možnosti kompilátoru C#)](/dotnet/csharp/language-reference/compiler-options/optimize-compiler-option).

## <a name="errors-and-warnings"></a>Chyby a upozornění
Následující nastavení se používají ke konfiguraci možnosti chyby a upozornění pro proces sestavení.

**Úroveň upozornění** určuje úroveň, která se zobrazí upozornění kompilátoru. Další informace najdete v tématu [/ warn (možnosti kompilátoru C#)](/dotnet/csharp/language-reference/compiler-options/warn-compiler-option).

**Potlačení upozornění** blokuje schopnost kompilátoru vygenerovat jeden nebo více upozorněními. Více čísel upozornění oddělte čárkou nebo středníkem. Další informace najdete v tématu [/nowarn (možnosti kompilátoru C#)](/dotnet/csharp/language-reference/compiler-options/nowarn-compiler-option).

## <a name="treat-warnings-as-errors"></a>Zpracovávat upozornění jako chyby
Následující nastavení se používají k určení, které upozornění jsou považovány za chyby. Vyberte jednu z následujících možností označíte, za jakých podmínek se má vrátit chybu při sestavení zaznamená upozornění. Další informace najdete v tématu [/warnaserror (možnosti kompilátoru C#)](/dotnet/csharp/language-reference/compiler-options/warnaserror-compiler-option).

**Žádný** zpracovává žádná upozornění jako chyby.

**Konkrétní varování** zpracovává zadaný upozornění jako chyby. Více čísel upozornění oddělte čárkou nebo středníkem.

**Všechny** zpracovává všech upozornění jako chyby.

## <a name="output"></a>Výstup
Následující nastavení se používají ke konfiguraci výstupní možnosti procesu sestavení.

**Výstupní cesta** Určuje umístění výstupní soubory pro konfiguraci tohoto projektu. Zadejte cestu k výstupu sestavení v tomto poli, nebo zvolte **Procházet** tlačítko zadejte cestu. Všimněte si, že cesta je relativní; Pokud chcete zadat absolutní cestu, bude uložen jako relativní. Výchozí cesta je bin\Debug nebo bin\Release\\.

S konfigurací zjednodušené sestavení projektu systému určuje, zda sestavování ladění a vydání verze. **Sestavení** příkaz **ladění** nabídky (F5) bude umístěte sestavení do umístění ladění, bez ohledu na to **výstupní cesta** zadáte. Ale **sestavení** příkaz **sestavení** nabídky vloží ho do umístění, které zadáte. Další informace najdete v tématu [Principy konfigurací sestavení](../../ide/understanding-build-configurations.md).

**Souborů dokumentace XML** Určuje název souboru, do které dokumentaci se zpracují komentáře. Další informace najdete v tématu [/DOC (možnosti kompilátoru C#)](/dotnet/csharp/language-reference/compiler-options/doc-compiler-option).

**Registrace pro zprostředkovatel komunikace s objekty COM** označuje, že ve spravované aplikaci zveřejní objektu COM (Obálka volatelná aplikacemi COM), který umožňuje objektu COM k interakci se ve spravované aplikaci. **Výstupní typ** vlastnost [stránky aplikace](../../ide/reference/application-page-project-designer-visual-basic.md) z **Návrhář projektu** pro tuto aplikaci musí být nastavené na **knihovny tříd** v pořadí pro **zaregistrovat zprostředkovatel komunikace s objekty COM** vlastnost, která má být k dispozici. Pro příklad třídu, která by mohla zahrnovat ve vaší [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] aplikace a zveřejněte jako objekt COM, najdete v části [Ukázka třídy COM](/dotnet/csharp/programming-guide/interop/example-com-class).

**Generovat sestavení serializace** Určuje, zda kompilátor použije k vytvoření sestavení serializace XML nástroje Generátor serializátor XML (Sgen.exe). Sestavení serializace může zlepšit výkon spuštění <xref:System.Xml.Serialization.XmlSerializer> Pokud jste použili třídy k serializaci typů v kódu. Ve výchozím nastavení je tato možnost nastavena na **automaticky**, která určuje, že sestavení serializace generováno pouze v případě, že jste použili <xref:System.Xml.Serialization.XmlSerializer> ke kódování typy v kódu jazyka XML. **Vypnout** Určuje, že sestavení serializace nikdy vydána, bez ohledu na to, jestli váš kód používá <xref:System.Xml.Serialization.XmlSerializer>. **Na** Určuje, že sestavení serializace vždy vygenerovat. Sestavení serializace jsou pojmenované `TypeName`. XmlSerializers.dll. Další informace najdete v tématu [nástroje Generátor serializátor XML (Sgen.exe)](/dotnet/framework/serialization/xml-serializer-generator-tool-sgen-exe).

**Upřesnit** kliknutím zobrazíte [Advanced sestavení dialogové okno nastavení (C#)](../../ide/reference/advanced-build-settings-dialog-box-csharp.md) dialogové okno.

## <a name="see-also"></a>Viz také

- [Referenční dokumentace k vlastnostem projektu](../../ide/reference/project-properties-reference.md)
- [Možnosti kompilátoru jazyka C#](/dotnet/csharp/language-reference/compiler-options/index)