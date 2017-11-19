---
title: "CA1824: Označte sestavení pomocí atributu NeutralResourcesLanguageAttribute | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1824
- MarkAssembliesWithNeutralResourcesLanguage
helpviewer_keywords:
- MarkAssembliesWithNeutralResourcesLanguage
- CA1824
ms.assetid: 10e97f8a-aa6e-47aa-b253-1e5d3a295d82
caps.latest.revision: "12"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: c1d2138065946bfd14abfedbbffdd2dc5b433d89
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="ca1824-mark-assemblies-with-neutralresourceslanguageattribute"></a>CA1824: Označte sestavení pomocí atributu NeutralResourcesLanguageAttribute
|||  
|-|-|  
|TypeName|MarkAssembliesWithNeutralResourcesLanguage|  
|CheckId|CA1824|  
|Kategorie|Microsoft.Performance|  
|Narušující změna|Nenarušující|  
  
## <a name="cause"></a>příčina  
 Obsahuje sestavení **ResX**– na základě prostředků, ale nemá <xref:System.Resources.NeutralResourcesLanguageAttribute?displayProperty=fullName> použije na ni.  
  
## <a name="rule-description"></a>Popis pravidla  
 **NeutralResourcesLanguage** informuje atribut **ResourceManager** jazyka, který se používá k zobrazení prostředků neutrální jazykovou verzi pro sestavení. Když dojde k vyhledání prostředků v stejnou jazykovou verzi jako jazyk neutrální prostředky **ResourceManager** automaticky používá prostředky, které jsou umístěné v hlavní sestavení. Dělá to namísto hledání pro satelitní sestavení, který má aktuální prostředí uživatelského rozhraní pro aktuální vlákno. To zlepšuje výkon vyhledávání při prvním získání prostředků a může zmenšit vaši pracovní sadu.  
  
## <a name="fixing-violations"></a>Opravit porušení  
 Opravit porušení toto pravidlo, přidejte atribut do sestavení a zadat jazyk prostředků neutrální jazykové verze.  
  
## <a name="specifying-the-language"></a>Určení jazyka  
  
#### <a name="to-specify-the-language-of-the-resource-of-the-neutral-culture"></a>Chcete-li určit jazyk prostředků neutrální jazykové verze  
  
1.  V **Průzkumníku řešení**, klikněte pravým tlačítkem na projekt a pak klikněte na tlačítko **vlastnosti**.  
  
2.  V levém navigačním panelu vyberte **aplikace**a potom klikněte na **informací o sestavení**.  
  
3.  V **informací o sestavení** dialogovém okně vyberte jazyk z **neutrální jazyk** rozevíracího seznamu.  
  
4.  Click **OK**.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Je přípustné upozornění toto pravidlo potlačit. Ale může snížit výkon při spouštění.