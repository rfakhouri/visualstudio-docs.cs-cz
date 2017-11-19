---
title: "CA1725: Názvy parametrů by měl odpovídat základní deklaraci | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ParameterNamesShouldMatchBaseDeclaration
- CA1725
helpviewer_keywords:
- CA1725
- ParameterNamesShouldMatchBaseDeclaration
ms.assetid: 9b657ab0-fe81-4f4c-9481-ba746988c922
caps.latest.revision: "11"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 3e8fc1a5f3623f989341f147ce8043449ee49165
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="ca1725-parameter-names-should-match-base-declaration"></a>CA1725: Názvy parametrů by měly odpovídat základní deklaraci
|||  
|-|-|  
|TypeName|ParameterNamesShouldMatchBaseDeclaration|  
|CheckId|CA1725|  
|Kategorie|Microsoft.Naming|  
|Narušující změna|Narušující|  
  
## <a name="cause"></a>příčina  
 Název parametru v přepsání externě viditelné metoda neodpovídá názvu parametru v základní deklaraci metody nebo název parametru v deklaraci rozhraní metody.  
  
## <a name="rule-description"></a>Popis pravidla  
 Konzistentní pojmenování parametrů v hierarchii přetěžování zvyšuje použitelnost přetížení metody. Název parametru, který se v odvozené metodě liší od názvu v základní deklaraci, může způsobit zmatení, zda se u metody jedná o přepis základní metody, nebo o nové přetížení metody.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Chcete-li opravit porušení toto pravidlo, přejmenujte parametru odpovídat základní deklaraci. Je narušující změně pro metody viditelné modelu COM.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Není potlačit upozornění na toto pravidlo s výjimkou metody viditelné modelu COM v knihovnách, které byly dříve součástí.