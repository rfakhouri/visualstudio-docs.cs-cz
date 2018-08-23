---
title: 'CA1409: Viditelné typy modelu Com by měly být vytvořitelné | Dokumentace Microsoftu'
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
ms.openlocfilehash: 06f4b5c2432e6aba39408a39afdf9870b5479fbb
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42696263"
---
# <a name="ca1409-com-visible-types-should-be-creatable"></a>CA1409: Viditelné typy modelu COM by měly být vytvořitelné
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [CA1409: viditelné typy modelu Com by měly být vytvořitelné](https://docs.microsoft.com/visualstudio/code-quality/ca1409-com-visible-types-should-be-creatable).  
  
TypeName | ComVisibleTypesShouldBeCreatable |  
| ID kontroly | CA1409 |  
| Kategorie | Microsoft.Interoperability|  
| Zásadní změna | Ukončování bez |  
  
## <a name="cause"></a>příčina  
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
 [Kvalifikace typů .NET pro spolupráci](http://msdn.microsoft.com/library/4b8afb52-fb8d-4e65-b47c-fd82956a3cdd)   
 [Spolupráce s nespravovaným kódem](http://msdn.microsoft.com/library/ccb68ce7-b0e9-4ffb-839d-03b1cd2c1258)



