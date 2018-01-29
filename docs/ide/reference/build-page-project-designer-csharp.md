---
title: "Stránka sestavení, Návrhář projektu (C#) | Microsoft Docs"
ms.custom: 
ms.date: 06/20/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- cs.ProjectPropertiesBuild
helpviewer_keywords:
- Build options [C#]
- Project Designer, Build page
ms.assetid: 77ff1bfc-d633-4634-ba29-9afdb6d7e362
caps.latest.revision: 
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- dotnet
ms.openlocfilehash: 233bb7516678888a2c7c4e6ec0b1b4f7d21b1393
ms.sourcegitcommit: b18844078a30d59014b48a9c247848dea188b0ee
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/29/2018
---
# <a name="build-page-project-designer-c"></a>Stránka Sestavení, návrhář projektu (C#)
Použití **sestavení** stránky **Návrhář projektu** zadat vlastnosti konfigurace sestavení projektu. Tato stránka se vztahuje na [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] pouze projekty.  

Pro přístup k **sestavení** vyberte uzel projektu (ne **řešení** uzel) v **Průzkumníku řešení**. Zvolte **zobrazení**, **stránky vlastností** v nabídce. Jakmile se zobrazí v Návrháři projektu, vyberte **sestavení** kartě.  

[!INCLUDE[note_settings_general](../../data-tools/includes/note_settings_general_md.md)]  

## <a name="configuration-and-platform"></a>Konfigurace a platformy  
Následující možnosti vám umožňuje vybrat konfigurace a platformy můžete zobrazit nebo upravit.  

> [!NOTE]
> S konfigurací zjednodušené sestavení projektu systému určuje, zda sestavování ladění a vydání verze. Proto tyto možnosti nezobrazí. Další informace najdete v tématu [postupy: nastavení ladění a konfigurace verze](/debugger/how-to-set-debug-and-release-configurations.md).

**Konfigurace**  
Určuje nastavení konfigurace, které chcete zobrazit nebo změnit. Toto nastavení může být **aktivní (ladění)** (Toto je výchozí nastavení), **ladění**, **verze**, nebo **všechny konfigurace**.  

**Platforma**  
Určuje nastavení platformy, které chcete zobrazit nebo změnit. Ve výchozím nastavení je **aktivní (jakýkoli procesor)**. Můžete změnit pomocí active platformy **nástroje Configuration Manager**. Další informace najdete v tématu [postupy: vytvoření a úprava konfigurací](../../ide/how-to-create-and-edit-configurations.md).  

## <a name="general"></a>Obecné  
Následující možnosti vám umožňují konfigurovat několik nastavení kompilátoru C#.  

**Podmíněná kompilace symboly**  
Určuje, které se má provést Podmíněná kompilace symbolů. Symboly oddělujte středníkem (";"). Další informace najdete v tématu [/ define (možnosti kompilátoru C#)](/dotnet/csharp/language-reference/compiler-options/define-compiler-option).  

**Definování ladění konstanta**  
Definuje ladění jako symbol v všechny soubory zdrojového kódu ve vaší aplikaci. Vyberete tuto možnost je ekvivalentní k použití `/define:DEBUG` možnost příkazového řádku.  

**Definování trasování konstanta**  
Definuje pravidla pro trasování jako symbol v všechny soubory zdrojového kódu ve vaší aplikaci. Vyberete tuto možnost je ekvivalentní k použití `/define:TRACE` možnost příkazového řádku.  

**Cílová platforma**  
Určuje procesoru, které se zaměřují výstupní soubor. Zvolte **x86** pro jakýkoli 32-bit Intel kompatibilní procesor, zvolte **x64** žádné 64bitový procesor Intel kompatibilní, zvolte **ARM** pro procesory ARM, nebo zvolte  **Všechny procesoru** k určení, že jakýkoli procesor je přijatelná. **Všechny procesoru** je výchozí hodnota pro projekty, protože umožňuje aplikaci, aby běžela na nejširší řadu hardwaru.  

Další informace najdete v tématu [/Platform (možnosti kompilátoru C#)](/dotnet/csharp/language-reference/compiler-options/platform-compiler-option).  

**Dáváte přednost 32-bit**  
Pokud **Prefer32 bitů** je zaškrtnuté políčko, je aplikace spuštěná jako 32bitová aplikace na 32bitové a 64bitové verze systému Windows. Pokud není políčko zaškrtnuto, aplikace se spouští jako 32bitová aplikace na 32bitové verze systému Windows a jako 64bitové aplikaci v 64bitových verzích systému Windows.  

Pokud spouštíte aplikaci jako 64bitové aplikaci velikost zdvojnásobí ukazatele, a mohou nastat problémy s kompatibilitou u další knihovny, které jsou výhradně 32-bit. Je užitečné k 64bitové aplikaci spustit, jenom v případě, že je více než 4 GB paměti nebo 64-bit pokynů zadejte zlepšování významně zvýšit výkon.  

Toto zaškrtávací políčko je dostupné jenom v případě, že jsou splněny všechny následující podmínky:  

-   Na **stránku sestavení**, **Cílová platforma** seznamu je nastavena na **libovolný procesor**.  

-   Na **stránky aplikace**, **výstupní typ** seznamu určuje, že je projekt aplikace.  

-   Na **stránky aplikace**, **cílové rozhraní** seznamu určuje rozhraní .NET Framework 4.5.  


**Povolit nezabezpečený kód**  
Umožňuje kód, který používá [unsafe](/dotnet/csharp/language-reference/keywords/unsafe) – klíčové slovo zkompilovat. Další informace najdete v tématu [/ unsafe (možnosti kompilátoru C#)](/dotnet/csharp/language-reference/compiler-options/unsafe-compiler-option).  

**Optimalizace kódu**  
Povolit nebo zakázat optimalizace provádí kompilátoru k vytvoření výstupního souboru menší, rychlejší a efektivnější. Další informace najdete v tématu [/ optimize (možnosti kompilátoru C#)](/dotnet/csharp/language-reference/compiler-options/optimize-compiler-option).  

## <a name="errors-and-warnings"></a>Chyby a upozornění  
Následující nastavení se používají ke konfiguraci možnosti chyby a upozornění pro proces sestavení.  

**Úroveň upozornění**  
Určuje úroveň k zobrazení upozornění kompilátoru. Další informace najdete v tématu [/ warn (možnosti kompilátoru C#)](/dotnet/csharp/language-reference/compiler-options/warn-compiler-option).  

**Potlačení upozornění**  
Blokuje schopnost kompilátoru vygenerovat jeden nebo více upozorněními. Více čísel upozornění oddělte čárkou nebo středníkem. Další informace najdete v tématu [/nowarn (možnosti kompilátoru C#)](/dotnet/csharp/language-reference/compiler-options/nowarn-compiler-option).  

## <a name="treat-warnings-as-errors"></a>Zpracovávat upozornění jako chyby  
Následující nastavení se používají k určení, které upozornění jsou považovány za chyby. Vyberte jednu z následujících možností označíte, za jakých podmínek se má vrátit chybu při sestavení zaznamená upozornění. Další informace najdete v tématu [/warnaserror (možnosti kompilátoru C#)](/dotnet/csharp/language-reference/compiler-options/warnaserror-compiler-option).  

**None**  
Zpracovává žádná upozornění jako chyby.  

**Konkrétní varování**  
Zpracuje zadané upozornění jako chyby. Více čísel upozornění oddělte čárkou nebo středníkem.  

**Všechny**  
Zpracovává všechny upozornění jako chyby.  

## <a name="output"></a>Výstup  
Následující nastavení se používají ke konfiguraci výstupní možnosti procesu sestavení.  

**Výstupní cesta**  
Určuje umístění výstupních souborů pro tento projekt konfiguraci. Zadejte cestu k výstupu sestavení v tomto poli, nebo zvolte **Procházet** tlačítko zadejte cestu. Všimněte si, že cesta je relativní; Pokud chcete zadat absolutní cestu, bude uložen jako relativní. Výchozí cesta je bin\Debug nebo bin\Release\\.

S konfigurací zjednodušené sestavení projektu systému určuje, zda sestavování ladění a vydání verze. **Sestavení** příkaz **ladění** nabídky (F5) bude umístěte sestavení do umístění ladění, bez ohledu na to **výstupní cesta** zadáte. Ale **sestavení** příkaz **sestavení** nabídky vloží ho do umístění, které zadáte. Další informace najdete v tématu [Principy konfigurací sestavení](../../ide/understanding-build-configurations.md).

**Souborů dokumentace XML**  
Určuje název souboru, do které dokumentaci se zpracují komentáře. Další informace najdete v tématu [/DOC (možnosti kompilátoru C#)](/dotnet/csharp/language-reference/compiler-options/doc-compiler-option).  

**Registrace pro zprostředkovatel komunikace s objekty COM**  
Označuje, že ve spravované aplikaci zveřejní objektu COM (Obálka volatelná aplikacemi COM), který umožňuje objektu COM k interakci se ve spravované aplikaci. **Výstupní typ** vlastnost [stránky aplikace](../../ide/reference/application-page-project-designer-visual-basic.md) z **Návrhář projektu** pro tuto aplikaci musí být nastavené na **knihovny tříd** v pořadí pro **zaregistrovat zprostředkovatel komunikace s objekty COM** vlastnost, která má být k dispozici. Pro příklad třídu, která by mohla zahrnovat ve vaší [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] aplikace a zveřejněte jako objekt COM, najdete v části [Ukázka třídy COM](/dotnet/csharp/programming-guide/interop/example-com-class).  

**Generovat sestavení serializace**  
Určuje, zda kompilátor použije k vytvoření sestavení serializace XML nástroje Generátor serializátor XML (Sgen.exe). Sestavení serializace může zlepšit výkon spuštění <xref:System.Xml.Serialization.XmlSerializer> Pokud jste použili třídy k serializaci typů v kódu. Ve výchozím nastavení je tato možnost nastavena na **automaticky**, která určuje, že sestavení serializace generováno pouze v případě, že jste použili <xref:System.Xml.Serialization.XmlSerializer> ke kódování typy v kódu jazyka XML. **Vypnout** Určuje, že sestavení serializace nikdy vydána, bez ohledu na to, jestli váš kód používá <xref:System.Xml.Serialization.XmlSerializer>. **Na** Určuje, že sestavení serializace vždy vygenerovat. Sestavení serializace jsou pojmenované `TypeName`. XmlSerializers.dll. Další informace najdete v tématu [nástroje Generátor serializátor XML (Sgen.exe)](/dotnet/framework/serialization/xml-serializer-generator-tool-sgen-exe).  

**Pokročilé**  
Kliknutím zobrazíte [Advanced sestavení dialogové okno nastavení (C#)](../../ide/reference/advanced-build-settings-dialog-box-csharp.md) dialogové okno.  

## <a name="see-also"></a>Viz také  
[Referenční dokumentace k vlastnostem projektu](../../ide/reference/project-properties-reference.md)   
[Možnosti kompilátoru jazyka C#](/dotnet/csharp/language-reference/compiler-options/index)
