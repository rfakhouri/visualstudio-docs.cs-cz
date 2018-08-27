---
title: 'CA1713: Události by neměly mít předponu před nebo po | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- EventsShouldNotHaveBeforeOrAfterPrefix
- CA1713
helpviewer_keywords:
- CA1713
- EventsShouldNotHaveBeforeOrAfterPrefix
ms.assetid: 855772a4-aa9e-410b-88c1-c5fba1ca63da
caps.latest.revision: 16
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 46ed0ad62d145b7c60c9f20e1a3770016098a236
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/24/2018
ms.locfileid: "42900470"
---
# <a name="ca1713-events-should-not-have-before-or-after-prefix"></a>CA1713: Události by neměly mít předponu před nebo po
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [CA1713: události by neměly mít předponu před nebo po](https://docs.microsoft.com/visualstudio/code-quality/ca1713-events-should-not-have-before-or-after-prefix).

|||
|-|-|
|TypeName|EventsShouldNotHaveBeforeOrAfterPrefix|
|CheckId|CA1713|
|Kategorie|Microsoft.Naming|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina
 Název události začíná 'Before' a 'After'.

## <a name="rule-description"></a>Popis pravidla
 Názvy událostí, měl by popisovat akce, která vyvolává událost. Pro pojmenování souvisejících událostí vyvolaných v určitém pořadí je vhodné používat přítomný a minulý čas, který naznačí relativní pozici v pořadí akcí. Například při pojmenování dvojice událostí, který je vyvolána při zavření prostředek, můžete pojmenovat ho "Zavřít" a "Uzavřeno" místo "BeforeClose" a "AfterClose".

 Zásady vytváření názvů poskytují obecný vzhled knihovnám využívajících common language runtime. To snižuje učit se, která vyžaduje nové knihovny softwaru a zvyšuje důvěru zákazníků, že byla vyvinuta knihovny někdo, kdo má odborných znalostí v vývoj spravovaného kódu.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Odebrání předpony názvu události a zvažte možnost změnit název, který má používat přítomný a minulý čas slovesa.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte upozornění na toto pravidlo.



