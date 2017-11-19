---
title: "CA1051: Nedeklarujte viditelná pole instance | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1051
- DoNotDeclareVisibleInstanceFields
helpviewer_keywords:
- CA1051
- DoNotDeclareVisibleInstanceFields
ms.assetid: 2805376c-824c-462c-81d1-c51aaf7cabe7
caps.latest.revision: "17"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: c80ac321100ecc0f88811332c73bdfd99b5a6a99
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="ca1051-do-not-declare-visible-instance-fields"></a>CA1051: Nedeklarujte viditelná pole instance
|||  
|-|-|  
|TypeName|DoNotDeclareVisibleInstanceFields|  
|CheckId|CA1051|  
|Kategorie|Microsoft.Design|  
|Narušující změna|Narušující|  
  
## <a name="cause"></a>příčina  
 Typ externě viditelné má poli externě viditelné instance.  
  
## <a name="rule-description"></a>Popis pravidla  
 Hlavní použití pole by mělo být jako podrobnost implementace. Pole by měla být `private` nebo `internal` a by měly být vystaveny pomocí vlastností. Je stejně snadná o přístup k vlastnosti, jako je přístup k poli a kód v přístupové objekty vlastnosti můžete změnit podle funkce typu rozbalte bez zavedení nejnovější změny. Vlastnosti, které právě vrátí hodnotu pole soukromý nebo interní jsou optimalizované pro provedení srovnatelné s přístup k poli. prostřednictvím vlastnosti je přidružen k použití externě viditelná pole výkonu zanedbatelné.  
  
 Externě viditelné odkazuje na `public`, `protected`, a `protected internal` (`Public`, `Protected`, a `Protected Friend` v jazyce Visual Basic) úrovní přístupu.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Opravit porušení toto pravidlo, ujistěte se, pole `private` nebo `internal` a vystavit pomocí externě viditelné vlastnosti.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Nepotlačujte upozornění na toto pravidlo. Externě viditelná pole neposkytují žádné výhody, které jsou k dispozici na vlastnosti. Kromě toho veřejná pole nemůže být chráněn [požadavky propojení](/dotnet/framework/misc/link-demands). V tématu [CA2112: zabezpečené typy by neměly vystavovat pole](../code-quality/ca2112-secured-types-should-not-expose-fields.md).  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje typ (`BadPublicInstanceFields`) porušil toto pravidlo. `GoodPublicInstanceFields`Zobrazuje opravené kód.  
  
 [!code-csharp[FxCop.Design.TypesPublicInstanceFields#1](../code-quality/codesnippet/CSharp/ca1051-do-not-declare-visible-instance-fields_1.cs)]  
  
## <a name="related-rules"></a>Související pravidla  
 [CA2112: Zabezpečené typy by neměly vystavovat pole](../code-quality/ca2112-secured-types-should-not-expose-fields.md)  
  
## <a name="see-also"></a>Viz také  
 [Požadavky na odkaz](/dotnet/framework/misc/link-demands)