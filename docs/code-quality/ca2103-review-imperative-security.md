---
title: 'CA2103: Zkontrolujte naléhavé zabezpečení | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- CA2103
- ReviewImperativeSecurity
helpviewer_keywords:
- CA2103
- ReviewImperativeSecurity
ms.assetid: d24fde71-bdf6-46c0-8965-9a73dc33c1aa
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f5a46629efacc37af593e4cd7487b69031cf6bb1
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="ca2103-review-imperative-security"></a>CA2103: Revize naléhavého zabezpečení
|||  
|-|-|  
|TypeName|ReviewImperativeSecurity|  
|CheckId|CA2103|  
|Kategorie|Microsoft.Security|  
|Narušující změna|Narušující|  
  
## <a name="cause"></a>příčina  
 Metoda používá imperativní zabezpečení a může vytvářet oprávnění pomocí stavové informace nebo návratové hodnoty, která se může změnit, pokud je žádost aktivní.  
  
## <a name="rule-description"></a>Popis pravidla  
 Naléhavého zabezpečení používá spravované objekty k zadání oprávnění a akce zabezpečení při spuštění kódu ve srovnání s deklarativní zabezpečení, která využívá atributy pro uložení oprávnění a akce v metadatech. Naléhavého zabezpečení je velmi flexibilní, protože můžete nastavit stav objektu oprávnění a výběr akce zabezpečení pomocí informace, které jsou k dispozici až běhu. Společně s, který se dodává flexibilitu riziko, že informace o běhu programu, který použijete k určení, že stav oprávnění není zůstanou beze změny, dokud akce je v platnosti.  
  
 Používejte deklarativní zabezpečení vždy, když je to možné. Deklarativní požadavky jsou lépe pochopit.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Zkontrolujte naléhavé zabezpečení požadavky a ujistěte se, že stav oprávnění nespoléhá se na informace, které můžete změnit, dokud se používá tato oprávnění.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Je bezpečné potlačit upozornění na toto pravidlo, je-li oprávnění nevyžaduje změny dat. Je nicméně lepší změnit imperativní požadavek na ekvivalentní deklarativní.  
  
## <a name="see-also"></a>Viz také  
 [Pokyny pro zabezpečené kódování](/dotnet/standard/security/secure-coding-guidelines)   
 [Data a modelování](/dotnet/framework/data/index)