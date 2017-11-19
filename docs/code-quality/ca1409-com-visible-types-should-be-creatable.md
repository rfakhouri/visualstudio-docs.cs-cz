---
title: "CA1409: Viditelné typy modelu Com by měly být vytvořitelné | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ComVisibleTypesShouldBeCreatable
- CA1409
helpviewer_keywords:
- ComVisibleTypesShouldBeCreatable
- CA1409
ms.assetid: 9f59569b-de15-4a38-b7cb-cff152972243
caps.latest.revision: "18"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: c8d9fe357142cf8b95be0298797c4a18e9ee0df7
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
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
 [Kvalifikace typů .NET pro spolupráci](/dotnet/framework/interop/qualifying-net-types-for-interoperation)   
 [Spolupráce s nespravovaným kódem](/dotnet/framework/interop/index)