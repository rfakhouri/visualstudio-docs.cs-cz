---
title: 'CA2210: Sestavení by měly mít platné silné názvy'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- AssembliesShouldHaveValidStrongNames
- CA2210
helpviewer_keywords:
- AssembliesShouldHaveValidStrongNames
- CA2210
ms.assetid: 8ed33d1c-8ec6-4b47-a692-e22dc8693088
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 7b7fb5f55ee345fa47a4a4510fe8121b82d1c0ae
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31919635"
---
# <a name="ca2210-assemblies-should-have-valid-strong-names"></a>CA2210: Sestavení by měly mít platné silné názvy
|||
|-|-|
|TypeName|AssembliesShouldHaveValidStrongNames|
|CheckId|CA2210|
|Kategorie|Microsoft.Design|
|Narušující změna|Bez ukončování řádků|

## <a name="cause"></a>příčina
 Sestavení není podepsáno silným názvem, nebylo možné ověřit silný název nebo silným názvem nebude platný bez aktuální nastavení registru počítače.

## <a name="rule-description"></a>Popis pravidla
 Toto pravidlo načte a ověřuje silný název sestavení. Dojde k narušení, pokud platí některá z následujících akcí:

-   Sestavení nemá silný název.

-   Po podepsání byla změněna sestavení.

-   Sestavení je podepsaný zpoždění.

-   Nesprávně podepsaná sestavení nebo podepisování se nezdařilo.

-   Sestavení vyžaduje nastavení registru předat ověření. Například nástroj silného názvu (Sn.exe) byl použit pro přeskočení ověření pro sestavení.

 Silný název chrání klienty před neúmyslným načtením narušeného sestavení. Sestavení bez silných názvů by kromě velmi omezených scénářů neměla být nasazována. Pokud sdílíte nebo šíříte sestavení, která nejsou správně podepsána, může být sestavení záměrně poškozeno, modul CLR je nemusí načíst nebo uživatelé mohou být nuceni vypnout na svém počítači ověřování. Sestavení bez silným názvem má z následující nevýhody:

-   Nelze ověřit jeho zdroje.

-   Modul CLR nelze upozornit uživatele, pokud obsah sestavení bylo změněno.

-   Nebylo možné načíst do globální mezipaměti sestavení.

 Všimněte si, že se načíst a analyzovat sestavení se zpožděním podepsané, je nutné zakázat ověření pro sestavení.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 **Vytvořte soubor klíče**

 Použijte jednu z následujících postupů:

-   Použití nástroje Linker sestavení (Al.exe) poskytované [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] SDK.

-   Pro [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] verze 1.0 nebo verze 1.1, použijte buď <xref:System.Reflection.AssemblyKeyFileAttribute?displayProperty=fullName> nebo <xref:System.Reflection.AssemblyKeyNameAttribute?displayProperty=fullName> atribut.

-   Pro [!INCLUDE[dnprdnlong](../code-quality/includes/dnprdnlong_md.md)], použijte buď `/keyfile` nebo `/keycontainer` – možnost kompilátoru [/keyfile (zadat klíč nebo pár klíč pro podepsání sestavení)](/cpp/build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly) nebo  [ /keycontainer (zadat kontejner klíče pro podepsání sestavení)](/cpp/build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly) v jazyce C++ – možnost linkeru).

 **Podepsat své sestavení se silným názvem v sadě Visual Studio**

1.  V [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], otevřete řešení.

2.  V **Průzkumníku řešení**, klikněte pravým tlačítkem na projekt a pak klikněte na tlačítko **vlastnosti.**

3.  Klikněte na tlačítko **podpisování** a vyberte **podepsání sestavení** zaškrtávací políčko.

4.  Z **vyberte soubor klíče se silným názvem**, vyberte **nový**.

     **Vytvořit klíč se silným názvem** okně se zobrazí.

5.  V **název souboru klíče**, zadejte název složitý název klíče.

6.  Vyberte, jestli chcete chránit klíč s heslem a potom klikněte na **OK**.

7.  V **Průzkumníku řešení**, klikněte pravým tlačítkem na projekt a pak klikněte na tlačítko **sestavení**.

 **Podepsat své sestavení se silným názvem mimo Visual Studio**

-   Použijte nástroj pro silný název (Sn.exe), které poskytuje [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] SDK. Další informace najdete v tématu [Sn.exe (nástroj silným názvem)](/dotnet/framework/tools/sn-exe-strong-name-tool).

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Pouze potlačit upozornění na toto pravidlo, je-li sestavení slouží v prostředí, kde manipulaci s obsahem nehrají důležitou roli.

## <a name="see-also"></a>Viz také
 <xref:System.Reflection.AssemblyKeyFileAttribute?displayProperty=fullName> <xref:System.Reflection.AssemblyKeyNameAttribute?displayProperty=fullName> [Postupy: podepsání sestavení se silným názvem](/dotnet/framework/app-domains/how-to-sign-an-assembly-with-a-strong-name) [Sn.exe (nástroj pro silný název)](/dotnet/framework/tools/sn-exe-strong-name-tool)