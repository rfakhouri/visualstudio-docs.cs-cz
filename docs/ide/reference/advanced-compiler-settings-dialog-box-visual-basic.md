---
title: Dialogové okno Upřesnit nastavení kompilátoru (Visual Basic)
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- vb.ProjectPropertiesAdvancedCompile
helpviewer_keywords:
- Advanced Compiler Settings dialog box
ms.assetid: 1f81133a-293f-4dba-bc1c-8baafb01d857
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 593bb95e45ecdbda14eba49425ce5db08369e6cf
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31948376"
---
# <a name="advanced-compiler-settings-dialog-box-visual-basic"></a>Dialogové okno Upřesnit nastavení kompilátoru (Visual Basic)

Použití **AdvancedCompiler nastavení** dialogové okno s **Návrhář projektu** k určení rozšířenou vlastností konfigurace sestavení projektu. Toto dialogové okno se vztahují na projekty Visual Basic jenom.

## <a name="to-access-this-dialog-box"></a>Pro přístup k tohoto dialogového okna

1.  V **Průzkumníku řešení**, vyberte uzel projektu (ne **řešení** uzlu).

2.  Na **projektu** nabídky, klikněte na tlačítko **vlastnosti**. Když **Návrhář projektu** se zobrazí, klikněte na tlačítko **zkompilovat** kartě.

3.  Na [stránka kompilovat, Návrhář projektu (Visual Basic)](../../ide/reference/compile-page-project-designer-visual-basic.md), vyberte **konfigurace** a **platformy**. V konfigurace zjednodušené sestavení **konfigurace** a **platformy** seznamy nejsou zobrazeny. Další informace najdete v tématu [postupy: nastavení ladění a konfigurace verze](../../debugger/how-to-set-debug-and-release-configurations.md).

4.  Klikněte na tlačítko **rozšířené možnosti kompilace**.

[!INCLUDE[note_settings_general](../../data-tools/includes/note_settings_general_md.md)]

## <a name="optimizations"></a>Optimalizace

 Zadejte následující možnosti optimalizace, které může v některých případech zmenšit soubor programu, ujistěte se, program rychlejší nebo urychlení procesu sestavení.

**Odebrat kontroly přetečení celé číslo**

Toto políčko zaškrtnuto, ve výchozím nastavení povolena kontrola přetečení celé číslo. Výběrem tohoto zaškrtávacího políčka odebrat kontrola přetečení celé číslo. Pokud vyberete toto políčko, může být rychlejší výpočty celé číslo. Pokud odeberete přetečení kontrolu a datový typ kapacity přetečení, nesprávné výsledky může být uložený bez chyby vyvolaných.

Pokud jsou zaškrtnutá políčka přetečení podmínky a přetečení operace celé číslo, <xref:System.OverflowException> je vyvolána výjimka. V případě přetečení podmínky nejsou zaškrtnuté, nejsou některé operace celé číslo vyvolat výjimku.

**Povolit optimalizace**

Toto políčko zaškrtnuto, ve výchozím nastavení, zakázat optimalizace kompilátoru. Výběrem tohoto zaškrtávacího políčka Povolit optimalizace kompilátoru. Optimalizace kompilátoru byl výstupní soubor menší, rychlejší a efektivnější. Ale protože optimalizace způsobil změnu uspořádání kódu ve výstupním souboru, optimalizace kompilátoru mohou ztížit ladění.

 **Základní adresa knihovny DLL**

 Toto textové pole zobrazí výchozí základní adresa knihovny DLL v šestnáctkovém formátu. V projektech knihovny tříd a řízení knihovny můžete toto textové pole zadat základní adresu, který se má použít při vytváření knihovny DLL.

 **Generovat ladicí informace**

 Vyberte **žádné**, **úplné**, nebo **pouze pdb** ze seznamu. **Žádný** Určuje, že žádné informace o ladění generovat. **Úplné** Určuje, že úplné informace o ladění generovat, a **pouze pdb** Určuje, že by měl být vygenerován pouze PDB ladicí informace. Výchozí hodnota pro tuto možnost je **úplné**.

## <a name="compilation-constants"></a>Konstanty kompilace

Podmíněná kompilace konstanty mít vliv podobná pomocí [#Const](/dotnet/visual-basic/language-reference/directives/const-directive) direktivy preprocesoru ve zdroji souborů, s tím rozdílem, že definované konstanty jsou veřejné a platí pro všechny soubory v projektu. Podmíněná kompilace konstanty společně s použitím [#If... Then... #Else](/dotnet/visual-basic/language-reference/directives/if-then-else-directives) direktiva k Podmíněná kompilace zdrojové soubory. V tématu [Podmíněná kompilace](/dotnet/visual-basic/programming-guide/program-structure/conditional-compilation).

 **Definování ladění konstanta**

 Ve výchozím nastavení toto zaškrtávací políčko zaškrtnuto, zadání, aby bylo nastavené ladění konstanta.

 **Definování trasování konstanta**

 Ve výchozím nastavení toto zaškrtávací políčko zaškrtnuto, zadání, aby bylo nastavené trasování konstanta.

 **Vlastní konstanty**

 Zadejte všechny vlastní konstanty pro vaše aplikace v tomto poli. Položky musí být odděleny čárkami, pomocí tohoto formuláře: **Name1 = "Value1", NÁZEV2 = "Hodnota2", Name3 = "Hodnota3"**.

## <a name="other-settings"></a>Další nastavení

**Generování sestavení serializace**

Toto nastavení určuje, zda bude vytvořen sestavení serializace XML. Sestavení serializace může zlepšit výkon spuštění <xref:System.Xml.Serialization.XmlSerializer> Pokud třídy jste použili k serializaci typů v kódu. Výchozí hodnota pro tuto možnost je **automaticky**. **Automatické** Určuje, že sestavení serializace generováno pouze v případě, že jste použili <xref:System.Xml.Serialization.XmlSerializer> ke kódování typy v kódu jazyka XML. **Vypnout** Určuje, že sestavení serializace nikdy vydána, bez ohledu na to, jestli váš kód používá <xref:System.Xml.Serialization.XmlSerializer>. **Na** Určuje, že sestavení serializace vždy vygenerovat. Sestavení serializace jsou pojmenované `TypeName`. XmlSerializers.dll.

## <a name="see-also"></a>Viz také

- [Stránka Kompilovat, Návrhář projektu (Visual Basic)](../../ide/reference/compile-page-project-designer-visual-basic.md)