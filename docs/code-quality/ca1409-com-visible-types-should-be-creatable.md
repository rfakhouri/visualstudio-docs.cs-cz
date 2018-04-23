---
title: 'CA1409: Viditelné typy modelu COM by měly být vytvořitelné'
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- ComVisibleTypesShouldBeCreatable
- CA1409
helpviewer_keywords:
- ComVisibleTypesShouldBeCreatable
- CA1409
ms.assetid: 9f59569b-de15-4a38-b7cb-cff152972243
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8b2a7157c405eba52a2a7dc5de3b290a7ff26dc4
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="ca1409-com-visible-types-should-be-creatable"></a>CA1409: Viditelné typy modelu COM by měly být vytvořitelné
|||
|-|-|
|TypeName|ComVisibleTypesShouldBeCreatable|
|CheckId|CA1409|
|Kategorie|Microsoft.Interoperability|
|Narušující změna|Nenarušující|

## <a name="cause"></a>příčina
 Odkaz na typ, který je specificky označen jako viditelný na modelu COM (Component Object) obsahuje veřejný konstruktor parametrizované ale neobsahuje konstruktor veřejný výchozí (bez parametrů).

## <a name="rule-description"></a>Popis pravidla
 Klienti COM nelze vytvořit typ bez veřejný výchozí konstruktor. Však typ můžete dál přistupovat klienti COM Pokud jinými prostředky je možné vytvořit typ a předejte ji do klienta (například prostřednictvím návratovou hodnotu volání metody).

 Pravidlo ignoruje typy, které jsou odvozeny od <xref:System.Delegate?displayProperty=fullName>.

 Ve výchozím nastavení, jsou viditelné pro COM následující: sestavení, veřejné typy, členy veřejné instance ve veřejné typy a všichni členové typů veřejné hodnot.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení toto pravidlo, výchozí veřejný konstruktor přidat nebo odebrat <xref:System.Runtime.InteropServices.ComVisibleAttribute?displayProperty=fullName> z typu.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Je bezpečné potlačit upozornění na toto pravidlo, pokud jsou k dispozici další způsoby vytvoření a předat objekt COM klientovi.

## <a name="related-rules"></a>Související pravidla
 [CA1017: Označte sestavení pomocí atributu ComVisibleAttribute](../code-quality/ca1017-mark-assemblies-with-comvisibleattribute.md)

## <a name="see-also"></a>Viz také
 [Kvalifikace typů .NET pro spolupráci](/dotnet/framework/interop/qualifying-net-types-for-interoperation) [spolupráce pomocí nespravovaného kódu](/dotnet/framework/interop/index)