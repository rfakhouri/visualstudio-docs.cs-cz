---
title: 'CA1824: Označte sestavení pomocí NeutralResourcesLanguageAttribute'
ms.date: 03/29/2018
ms.topic: reference
f1_keywords:
- CA1824
- MarkAssembliesWithNeutralResourcesLanguage
helpviewer_keywords:
- MarkAssembliesWithNeutralResourcesLanguage
- CA1824
ms.assetid: 10e97f8a-aa6e-47aa-b253-1e5d3a295d82
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 40cb2a3674884a9fb4f1449c9afa2e0a2d27050f
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/08/2019
ms.locfileid: "55919141"
---
# <a name="ca1824-mark-assemblies-with-neutralresourceslanguageattribute"></a>CA1824: Označte sestavení pomocí NeutralResourcesLanguageAttribute

|||
|-|-|
|TypeName|MarkAssembliesWithNeutralResourcesLanguage|
|CheckId|CA1824|
|Kategorie|Microsoft.Performance|
|Narušující změna|Nenarušující|

## <a name="cause"></a>příčina

Obsahuje sestavení **ResX**– na základě zdrojů, ale nemá <xref:System.Resources.NeutralResourcesLanguageAttribute?displayProperty=fullName> použit.

## <a name="rule-description"></a>Popis pravidla

<xref:System.Resources.NeutralResourcesLanguageAttribute> Atribut informuje správce prostředků výchozí jazykové verze vaší aplikace. Pokud výchozí jazykové prostředky jsou vloženy do sestavení hlavní aplikace, a <xref:System.Resources.ResourceManager> má k načtení prostředků, které patří do stejné jazykovou verzi jako výchozí jazykovou verzi <xref:System.Resources.ResourceManager> automaticky používá prostředky umístěné v hlavním sestavení Namísto vyhledávání satelitního sestavení. Z toho půjde obchází obvykle sestavení testu, zlepšuje výkon vyhledávání při prvním získání prostředků můžete načíst a může zmenšit vaši pracovní sadu.

> [!TIP]
> Zobrazit [balení a nasazení prostředků](/dotnet/framework/resources/packaging-and-deploying-resources-in-desktop-apps) pro proces, který <xref:System.Resources.ResourceManager> používá pro sběr dat pro soubory prostředků.

## <a name="fix-violations"></a>Vyřešit porušení

Chcete-li opravit porušení tohoto pravidla, přidejte atribut sestavení a určit jazyk prostředků neutrální jazykovou verzi.

### <a name="to-specify-the-neutral-language-for-resources"></a>Chcete-li určit neutrální jazyk prostředků

1. V **Průzkumníka řešení**, klikněte pravým tlačítkem na projekt a pak vyberte **vlastnosti**.

2. Vyberte **aplikace** kartu a potom vyberte **informace o sestavení**.

   > [!NOTE]
   > Pokud váš projekt je projekt .NET Core nebo .NET Standard, vyberte **balíčku** kartu.

3. Vyberte jazyk ze **neutrální jazyk** nebo **neutrální jazyk sestavení** rozevíracího seznamu.

4. Vyberte **OK**.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Je přípustné potlačit upozornění tohoto pravidla. Však může snížit výkon při spuštění.

## <a name="see-also"></a>Viz také:

- <xref:System.Resources.NeutralResourcesLanguageAttribute>
- [Prostředky v aplikacích klasické pracovní plochy (.NET)](/dotnet/framework/resources/)
- [CA1703 - řetězce prostředků by měly být zadány správně](../code-quality/ca1703-resource-strings-should-be-spelled-correctly.md)
- [CA1701 - řetězec prostředku, který složených slov by měla správně formátováno.](../code-quality/ca1701-resource-string-compound-words-should-be-cased-correctly.md)