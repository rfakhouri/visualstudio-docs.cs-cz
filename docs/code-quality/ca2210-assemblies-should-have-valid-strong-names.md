---
title: 'CA2210: Sestavení by měla mít platné silné názvy'
ms.date: 11/04/2016
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
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 89edba30a95d61268aebb26de8d973f6201c0fcf
ms.sourcegitcommit: 5483e399f14fb01f528b3b194474778fd6f59fa6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/05/2019
ms.locfileid: "66714761"
---
# <a name="ca2210-assemblies-should-have-valid-strong-names"></a>CA2210: Sestavení by měla mít platné silné názvy

|||
|-|-|
|TypeName|AssembliesShouldHaveValidStrongNames|
|CheckId|CA2210|
|Kategorie|Microsoft.Design|
|Narušující změna|Pevné|

## <a name="cause"></a>Příčina

Sestavení není podepsáno silným názvem, silného názvu nelze ověřit nebo silný název autoritou nebude platný bez aktuální nastavení registru počítače.

## <a name="rule-description"></a>Popis pravidla

Toto pravidlo zjišťuje a ověří silný název sestavení. Porušení nastane, pokud je splněna některá z následujících akcí:

- Sestavení nemá silný název.

- Sestavení byl změněn po podepsání.

- Sestavení se zpožděným podpisem.

- Nesprávně podepsaná sestavení nebo podepisování selhalo.

- Sestavení vyžaduje nastavení registru úspěšně ověřen. Například nástroj Strong Name (Sn.exe) byla použita k přeskočení ověření pro sestavení.

Silný název chrání klienty před neúmyslným načtením narušeného sestavení. Sestavení bez silných názvů by kromě velmi omezených scénářů neměla být nasazována. Pokud sdílíte nebo šíříte sestavení, která nejsou správně podepsána, může být sestavení záměrně poškozeno, modul CLR je nemusí načíst nebo uživatelé mohou být nuceni vypnout na svém počítači ověřování. Sestavení bez silného názvu se z těchto nevýhod:

- Nelze ověřit jeho původu.

- Modul common language runtime nemůže upozornit uživatele, pokud obsah sestavení byl změněn.

- Nelze načíst do globální mezipaměti sestavení.

Všimněte si, že se načíst a analyzovat sestavení se zpožděným podpisem, je nutné zakázat ověřování pro sestavení.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení

### <a name="create-a-key-file"></a>Vytvořit soubor klíče

Použijte jednu z následujících postupů:

- Použití [nástroj Assembly Linker (Al.exe)](/dotnet/framework/tools/al-exe-assembly-linker).

- Pro rozhraní .NET Framework 2.0, použijte buď `/keyfile` nebo `/keycontainer` – možnost kompilátoru [/keyfile (zadat klíč nebo dvojici klíč k podepsání sestavení)](/cpp/build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly) nebo  [ /keycontainer (určení kontejneru klíčů pro podpis sestavení)](/cpp/build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly) – možnost linkeru v C++).

- Pro rozhraní .NET Framework v1.0 nebo v1.1, použijte buď <xref:System.Reflection.AssemblyKeyFileAttribute?displayProperty=fullName> nebo <xref:System.Reflection.AssemblyKeyNameAttribute?displayProperty=fullName> atribut.

### <a name="sign-your-assembly-with-a-strong-name-in-visual-studio"></a>Podepsání sestavení silným názvem v sadě Visual Studio

1. V sadě Visual Studio otevřete řešení.

2. V **Průzkumníka řešení**, klikněte pravým tlačítkem na projekt a potom klikněte na tlačítko **vlastnosti.**

3. Klikněte na tlačítko **podepisování** kartu a vyberte **podepsat sestavení** zaškrtávací políčko.

4. Z **vyberte soubor klíče se silným názvem**vyberte **nový**.

   **Vytvořit klíč se silným názvem** okně se zobrazí.

5. V **název souboru klíče**, zadejte název pro váš klíč se silným názvem.

6. Zvolte, jestli se k ochraně klíče s heslem a potom klikněte na **OK**.

7. V **Průzkumníka řešení**, klikněte pravým tlačítkem na projekt a potom klikněte na tlačítko **sestavení**.

### <a name="sign-your-assembly-with-a-strong-name-outside-visual-studio"></a>Podepsání sestavení silným názvem mimo sadu Visual Studio

Použití [nástroj Strong name (Sn.exe)](/dotnet/framework/tools/sn-exe-strong-name-tool).

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Pouze potlačit upozornění tohoto pravidla, pokud sestavení se používá v prostředí, kde manipulaci s obsahem není žádný problém.

## <a name="see-also"></a>Viz také:

- <xref:System.Reflection.AssemblyKeyFileAttribute?displayProperty=fullName>
- <xref:System.Reflection.AssemblyKeyNameAttribute?displayProperty=fullName>
- [Postupy: Podepsání sestavení silným názvem](/dotnet/framework/app-domains/how-to-sign-an-assembly-with-a-strong-name)
- [Sn.exe (nástroj pro silný název)](/dotnet/framework/tools/sn-exe-strong-name-tool)