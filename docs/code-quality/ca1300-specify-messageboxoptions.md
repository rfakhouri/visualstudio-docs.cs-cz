---
title: 'CA1300: Zadejte možnosti MessageBoxOptions'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- SpecifyMessageBoxOptions
- CA1300
helpviewer_keywords:
- SpecifyMessageBoxOptions
- CA1300
ms.assetid: 9357a724-026e-4a3d-a03a-f14635064ec6
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a8469deaf13c12200aec6a68eed9e78c4e9b8543
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31896987"
---
# <a name="ca1300-specify-messageboxoptions"></a>CA1300: Zadejte možnosti MessageBoxOptions
|||
|-|-|
|TypeName|SpecifyMessageBoxOptions|
|CheckId|CA1300|
|Kategorie|Microsoft.Globalization|
|Narušující změna|Nenarušující|

## <a name="cause"></a>příčina
 Metoda volá přetížení <xref:System.Windows.Forms.MessageBox.Show%2A?displayProperty=fullName> metoda, která nevyužívá <xref:System.Windows.Forms.MessageBoxOptions?displayProperty=fullName> argument.

## <a name="rule-description"></a>Popis pravidla
 Zobrazit okno se zprávou správně pro jazykové verze, které používají pořadí od čtení zprava doleva <xref:System.Windows.Forms.MessageBoxOptions> a <xref:System.Windows.Forms.MessageBoxOptions> členy <xref:System.Windows.Forms.MessageBoxOptions> – výčet musí být předán <xref:System.Windows.Forms.MessageBox.Show%2A> metoda. Zkontrolujte <xref:System.Windows.Forms.Control.RightToLeft%2A?displayProperty=fullName> vlastnost nadřazeného ovládacího prvku určit, jestli se má používat pořadí čtení zprava doleva.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení toto pravidlo, volejte přetížení <xref:System.Windows.Forms.MessageBox.Show%2A> metody, která přijímá <xref:System.Windows.Forms.MessageBoxOptions> argument.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Je bezpečné při knihovny kódu nebude možné lokalizovat pro jazykovou verzi, která používá pořadí čtení zprava doleva potlačit upozornění na toto pravidlo.

## <a name="example"></a>Příklad
 Následující příklad ukazuje metodu, která se zobrazí okno se zprávou, která obsahuje možnosti, které jsou vhodné pro čtení pořadí jazykovou verzi. Soubor na prostředek, který není zobrazený, je potřeba vytvořit v příkladu. Postupujte podle komentáře v příkladu k sestavení v příkladu bez souboru prostředků a k testování funkci zprava doleva.

 [!code-vb[FxCop.Globalization.SpecifyMBOptions#1](../code-quality/codesnippet/VisualBasic/ca1300-specify-messageboxoptions_1.vb)]
 [!code-csharp[FxCop.Globalization.SpecifyMBOptions#1](../code-quality/codesnippet/CSharp/ca1300-specify-messageboxoptions_1.cs)]

## <a name="see-also"></a>Viz také
 <xref:System.Resources.ResourceManager?displayProperty=fullName> [Prostředky v aplikacích klasické pracovní plochy](/dotnet/framework/resources/index)