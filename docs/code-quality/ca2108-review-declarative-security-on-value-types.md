---
title: "CA2108: Revize deklarativních zabezpečení u typů hodnot | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ReviewDeclarativeSecurityOnValueTypes
- CA2108
helpviewer_keywords:
- ReviewDeclarativeSecurityOnValueTypes
- CA2108
ms.assetid: d62bffdd-3826-4d52-a708-1c646c5d48c2
caps.latest.revision: "16"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: b05873b87767fa39cc6e0d675980bf658d76c584
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="ca2108-review-declarative-security-on-value-types"></a>CA2108: Revize deklarativních zabezpečení na hodnotách
|||  
|-|-|  
|TypeName|ReviewDeclarativeSecurityOnValueTypes|  
|CheckId|CA2108|  
|Kategorie|Microsoft.Security|  
|Narušující změna|Bez ukončování řádků|  
  
## <a name="cause"></a>příčina  
 Typ hodnoty veřejných nebo chráněného zabezpečené [Data a modelování](/dotnet/framework/data/index) nebo [požadavky propojení](/dotnet/framework/misc/link-demands).  
  
## <a name="rule-description"></a>Popis pravidla  
 Typy hodnot přidělovány a před provést další konstruktory inicializovat podle jejich výchozí konstruktory. Pokud typ hodnoty je zabezpečená službou na vyžádání nebo LinkDemand a volající nemá oprávnění, které odpovídají kontrola zabezpečení, všechny konstruktor jiné než výchozí se nezdaří a bude vyvolána výjimka zabezpečení. Typ hodnoty není navrácena; je ponechán ve stavu, která nastavuje jeho výchozí konstruktor. Nepředpokládejte, že volající, který předá instance typu hodnota má oprávnění vytvořit nebo získat přístup k instanci.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Narušení toto pravidlo nelze opravit, pokud kontrola zabezpečení odeberete z typu a použití zabezpečení na úrovni metoda zkontroluje na příslušné místo. Všimněte si, že opravit porušení tímto způsobem nezabrání volající s nedostatečná oprávnění získat instancí typ hodnoty. Můžete musí zkontrolujte, zda instance typu hodnotu ve svém výchozím stavu nevystavuje citlivé informace a nelze použít škodlivé způsobem.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Upozornění od tohoto pravidla můžete potlačit, pokud žádné volající můžete získat instance typu hodnotu ve svém výchozím stavu aniž představují ohrožení zabezpečení.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje knihovny obsahující typ hodnoty, která porušuje toto pravidlo. Všimněte si, že `StructureManager` typ předpokládá, že volající, který předá instance typu hodnota má oprávnění vytvořit nebo získat přístup k instanci.  
  
 [!code-csharp[FxCop.Security.DemandOnValueType#1](../code-quality/codesnippet/CSharp/ca2108-review-declarative-security-on-value-types_1.cs)]  
  
## <a name="example"></a>Příklad  
 Následující aplikace ukazuje slabé místo na knihovně.  
  
 [!code-csharp[FxCop.Security.TestDemandOnValueType#1](../code-quality/codesnippet/CSharp/ca2108-review-declarative-security-on-value-types_2.cs)]  
  
 Tento příklad vytvoří následující výstup.  
  
 **Struktura vlastní konstruktor: žádost se nezdařila.**  
**Nové hodnoty SecuredTypeStructure 100 100**  
**Nové hodnoty SecuredTypeStructure 200 200**   
## <a name="see-also"></a>Viz také  
 [Požadavky na odkaz](/dotnet/framework/misc/link-demands)   
 [Data a modelování](/dotnet/framework/data/index)