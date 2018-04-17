---
title: Soubory .NET pojmenování konvence pro EditorConfig | Microsoft Docs
ms.custom: ''
ms.date: 11/20/2017
ms.topic: conceptual
helpviewer_keywords:
- naming conventions [EditorConfig]
- EditorConfig naming conventions
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-ide-general
ms.workload:
- multiple
ms.openlocfilehash: 14b284c797add9545efdd291b06ce62b0b75cf03
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="net-naming-conventions-for-editorconfig"></a>Zásady vytváření názvů .NET pro EditorConfig

Zásady vytváření názvů se týkají pojmenování elementy kódu, jako jsou třídy, vlastnosti a metody. Například můžete zadat, že veřejné členy nutné velkými písmeny nebo asynchronní metody musí končit "Asynchronní". Tato pravidla můžete vynutit zadáním je [.editorconfig soubor](../ide/create-portable-custom-editor-options.md). Pojmenování porušení pravidel zobrazit buď v **seznam chyb** nebo jako návrh pod názvem, v závislosti na závažnosti můžete zvolit pravidla. Není nutné pro sestavení projektu chcete-li zobrazit narušení.

Zásady vytváření názvů by měla být seřazena z specifické pro většinu nejmenší na konkrétní v *.editorconfig* souboru. Je první pravidlo došlo k, který lze použít pouze pravidlo, které je použito.

Pro každé zásady vytváření názvů je nutné zadat symboly, které se vztahuje na, pojmenování styl a závažnost pro vynucení konvence, pomocí vlastností popsaných níže. Vlastnosti pořadí není důležité.

Pokud chcete začít, vyberte název vaší pojmenování pravidlo, které budete používat v každé vlastnosti, které jsou potřebné k plně zadejte popis pravidla. Například `public_members_must_be_capitalized` je dobrý název zásady vytváření pravidla. Budeme označovat název, vyberte jako **< namingRuleTitle\>**  v následujících částech.

## <a name="symbols"></a>Symboly

První Identifikujte skupinu symbolů pro pojmenování pravidlo použít. Tato vlastnost má následující formát:

`dotnet_naming_rule.<namingRuleTitle>.symbols = <symbolTitle>`

Zadejte název skupiny symbolů nahrazením **< symbolTitle\>**  hodnotu s popisný název, například `public_symbols`. Budete používat **< symbolTitle\>**  na (typy symbol, úrovní přístupu a modifikátory), je použita hodnota v názvech tři vlastnosti, které popisují, které symboly pravidlo.

### <a name="kinds-of-symbols"></a>Typy symbolů

K popisu druh symboly pro pojmenování pravidlo použít, zadejte vlastnosti v následujícím formátu:

`dotnet_naming_symbols.<symbolTitle>.applicable_kinds = <values>`

V následujícím seznamu jsou povolených hodnot, a zadáte více hodnot oddělených čárkami.

- \* (Tato hodnota slouží k určení všechny symboly)
- třída
- struct 
- rozhraní
- enum
- property
- – metoda
- pole
- event
- delegát
- parametr

### <a name="accessibility-levels-of-symbols"></a>Úrovně přístupnosti symbolů

Popis úrovní přístupu symbolů má pojmenování pravidlo použít, zadejte název vlastnosti v následujícím formátu:

`dotnet_naming_symbols.<symbolTitle>.applicable_accessibilities = <values>`

V následujícím seznamu jsou povolených hodnot, a zadáte více hodnot oddělených čárkami.

- \* (tuto hodnotu použijte k určení všech úrovní přístupu)
- public
- interní nebo friend
- private
- protected
- chráněné\_interní nebo protected_friend

> [!NOTE]
> Nezadávejte úroveň usnadnění přístupu v rámci zásady vytváření názvů, pokud není k dispozici na typ symbolu, které se zaměříte usnadnění. Například parametry nemají úrovní přístupu. Pokud zadáte úroveň usnadnění pro parametr zásady vytváření názvů, pojmenování pravidla nebude fungovat správně.

### <a name="symbol-modifiers"></a>Modifikátory – symbol

K popisu modifikátory symbolů má pojmenování pravidlo použít, zadejte název vlastnosti v následujícím formátu:

`dotnet_naming_symbols.<symbolTitle>.required_modifiers = <values>`

V následujícím seznamu jsou povolených hodnot, a zadáte více hodnot oddělených čárkami.

- abstraktní nebo must_inherit
- async
- const
- readonly
- statické nebo sdílené

`required_modifiers` Vlastnost je volitelná. Pokud ji vynecháte, bude použita pojmenování pravidla pro všechny modifikátory.

## <a name="style"></a>Styl

Teď, když jste si myslíme skupiny symbolů pro pojmenování pravidlo použít, jsme musí popisovat pojmenování styl. Styl může být, že název má určitá předponu nebo příponu určité nebo jednotlivých slov v názvu jsou odděleny určité znak. Můžete také určit styl malá a velká písmena. Vlastnost stylu má následující formát:

`dotnet_naming_rule.<namingRuleTitle>.style = <styleTitle>`

Pojmenujte styl nahrazením **< styleTitle\>**  hodnotu s popisný název, například `first_word_upper_case_style`. Budete používat **< styleTitle\>**  hodnota v názvy vlastností, které popisují styl pojmenování (předponu, příponu, word oddělovací znak a velkých písmen). Popište svou pomocí jednoho nebo více z těchto vlastností.

### <a name="require-a-prefix"></a>Vyžadovat předpony

K určení, že symbol názvy musí začínat některé znaky, použijte tuto vlastnost:

`dotnet_naming_style.<styleTitle>.required_prefix = <prefix>`

### <a name="require-a-suffix"></a>Požadavek na zadání přípony

Názvy symbolů musí končit některé znaky, pomocí této vlastnosti:

`dotnet_naming_style.<styleTitle>.required_suffix = <suffix>`

### <a name="require-a-certain-word-separator"></a>Vyžadovat určité slovo oddělovače

K určení, že jednotlivých slov v názvech symbol musí být odděleny s určitým znakem, použijte tuto vlastnost:

`dotnet_naming_style.<styleTitle>.word_separator = <separator character>`

### <a name="require-a-capitalization-style"></a>Vyžadovat použití velkých písmen styl

Určit styl konkrétní použití velkých písmen pro názvy symbolů, použijte tuto vlastnost:

`dotnet_naming_style.<styleTitle>.capitalization = <value>`

Povolené hodnoty pro tuto vlastnost jsou:

- pascal_case
- camel_case
- první\_word_upper
- všechny\_horní
- all_lower

> [!NOTE]
> Musíte zadat styl psaní velkých písmen v rámci vašeho pojmenování stylu, jinak vaše pojmenování styl může ignorovány.

## <a name="severity"></a>Závažnost

K popisu závažnost porušení pojmenování pravidla, určete vlastnost v následujícím formátu:

`dotnet_naming_rule.<namingRuleTitle>.severity = <value>`

Následující tabulka uvádí povolená závažnost hodnoty, a jejich významu:

Závažnost | Efekt
------------ | -------------
žádná nebo tichou | Když tento styl nedodržíte, nezobrazuje nic uživateli; automaticky generovaný kód však následuje tento styl.
Návrh | Pokud se tento styl nedodržíte, zobrazit uživateli jako návrh, jako základní tečky na první dva znaky. V době kompilace nemá žádný vliv.
upozornění | Při tomto stylu nedodržíte, zobrazovat upozornění kompilátoru v **seznam chyb**.
Chyba | Když tento styl nedodržíte, zobrazit chyba kompilátoru v **seznam chyb**.

> [!NOTE]
> Nemáte k sestavení projektu chcete-li zobrazit názvy porušení pravidel. Zobrazují se jako kód upravíte, buď v **seznam chyb** nebo jako návrh.

## <a name="example"></a>Příklad

Následující *.editorconfig* soubor obsahuje zásady vytváření názvů, který určuje, že veřejné vlastnosti, metody, pole, události a delegáti musí být velkými písmeny. Všimněte si, že tyto zásady vytváření názvů určuje více druhů symbol, který chcete použít pravidlo, pomocí oddělte hodnoty čárkami.

```EditorConfig
# Public members must be capitalized (public_members_must_be_capitalized)
[*.{cs,vb}]
dotnet_naming_rule.public_members_must_be_capitalized.symbols   = public_symbols
dotnet_naming_symbols.public_symbols.applicable_kinds           = property,method,field,event,delegate
dotnet_naming_symbols.public_symbols.applicable_accessibilities = public
dotnet_naming_symbols.public_symbols.required_modifiers         = readonly

dotnet_naming_rule.public_members_must_be_capitalized.style    = first_word_upper_case_style
dotnet_naming_style.first_word_upper_case_style.capitalization = first_word_upper

dotnet_naming_rule.public_members_must_be_capitalized.severity = suggestion
```

Následující snímek obrazovky ukazuje účinku zásad vytváření názvů v editoru. Dvě veřejné proměnné, které byly pojmenovány bez použití velkých písmen v první písmeno. Jedna je `const`, a jedna je `readonly`. Vzhledem k tomu, že pojmenování pravidlo se vztahuje pouze na `readonly` symboly pouze `readonly` proměnná ukazuje pojmenování návrhu pravidlo.

![Pojmenování pravidlo návrhu](media/editorconfig-naming-rule-suggestion.png)

Nyní změníme závažnost porušení na `warning`:

```EditorConfig
dotnet_naming_rule.public_members_must_be_capitalized.severity = warning
```

Pokud zavřete a otevřete váš soubor kódu, místo zobrazení návrhu v části název porušení, zobrazí zelená vlnovkou a upozornění v **seznam chyb**:

![Pojmenování pravidlo upozornění](media/editorconfig-naming-rule-warning.png)

## <a name="see-also"></a>Viz také

- [Jazyk rozhraní .NET a formátování konvence](../ide/editorconfig-code-style-settings-reference.md)
- [Vytvoření přenosné vlastního editoru možnosti](../ide/create-portable-custom-editor-options.md)
- [Soubor .editorconfig platformy .NET kompilátoru](https://github.com/dotnet/roslyn/blob/master/.editorconfig)
