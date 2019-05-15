---
title: 'CA1409: Viditelné typy modelu COM by měly být vytvořitelné | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- ComVisibleTypesShouldBeCreatable
- CA1409
helpviewer_keywords:
- ComVisibleTypesShouldBeCreatable
- CA1409
ms.assetid: 9f59569b-de15-4a38-b7cb-cff152972243
caps.latest.revision: 20
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 7bd52ad75c67f9c8faa80e84eb5ae09c22c25280
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2019
ms.locfileid: "65678880"
---
# <a name="ca1409-com-visible-types-should-be-creatable"></a>CA1409: Viditelné typy modelu COM by měly být vytvořitelné
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|ComVisibleTypesShouldBeCreatable|
|CheckId|CA1409|
|Kategorie|Microsoft.Interoperability|
|Narušující změna|Nenarušující|

## <a name="cause"></a>Příčina
 Odkaz na typ, který je označen jako viditelný pro Model COM (Component Object) obsahuje veřejný Parametrizovaný konstruktor, ale neobsahuje veřejný výchozí (bezparametrový) konstruktor.

## <a name="rule-description"></a>Popis pravidla
 Klienti modelu COM nelze vytvořit typ bez veřejného výchozího konstruktoru. Ale typ je pořád přístupný klientům modelu COM Pokud jiné znamená, že je k dispozici pro vytvoření typu a předejte jej do klienta (například prostřednictvím návratovou hodnotu volání metody).

 Pravidlo ignoruje typy, které jsou odvozeny z <xref:System.Delegate?displayProperty=fullName>.

 Ve výchozím nastavení, jsou následující viditelné modelu COM: sestavení, veřejné typy, členy veřejné instance ve veřejných typů a členů veřejných hodnotových typech.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, přidat veřejný výchozí konstruktor nebo odebrat <xref:System.Runtime.InteropServices.ComVisibleAttribute?displayProperty=fullName> z typu.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Je bezpečné potlačit upozornění tohoto pravidla, pokud jsou k dispozici další způsoby, jak vytvořit a předejte objekt klient modelu COM.

## <a name="related-rules"></a>Související pravidla
 [CA1017: Označte sestavení pomocí atributu ComVisibleAttribute](../code-quality/ca1017-mark-assemblies-with-comvisibleattribute.md)

## <a name="see-also"></a>Viz také
 [Kvalifikace typů .NET pro spolupráci](https://msdn.microsoft.com/library/4b8afb52-fb8d-4e65-b47c-fd82956a3cdd) [spolupráce pomocí nespravovaného kódu](https://msdn.microsoft.com/library/ccb68ce7-b0e9-4ffb-839d-03b1cd2c1258)
