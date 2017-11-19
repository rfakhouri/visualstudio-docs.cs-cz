---
title: "Určení, zda implementovat řízení VSPackage zdroje | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: source control packages, about source control packages
ms.assetid: 60b3326e-e7e2-4729-95fc-b682e7ad5c99
caps.latest.revision: "24"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 808f2fda26046962eada377f8a204351adef19bf
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="determining-whether-to-implement-a-source-control-vspackage"></a>Určení, zda implementovat řízení VSPackage zdroje
Tato část popisuje možnosti Zdroj ovládacího prvku zásuvné moduly a Správa zdrojového kódu VSPackages pro rozšíření řešení a nabízí rozsáhlé pokyny o výběru cestu vhodný integrace správy zdrojového kódu.  
  
## <a name="small-source-control-solution-with-limited-resources"></a>Řešením pro řízení malé zdroje s omezenou prostředky  
 Pokud máte omezený počet prostředků a nemůže burdened s nároky na zápis zdrojový řízení balíček, můžete vytvořit na základě zdroj ovládacího prvku Plug-in API modulů plug-in. Můžete tak pracovat node souběžně s balíčky zdroj ovládacího prvku a můžete přepínat mezi zdroj ovládacího prvku zásuvné moduly a balíčky na vyžádání. Další informace najdete v tématu [registrace a výběr](../../extensibility/internals/registration-and-selection-source-control-vspackage.md).  
  
## <a name="large-source-control-solution-with-a-rich-feature-set"></a>Řešením pro řízení velké zdroj sadou bohaté funkce  
 Pokud chcete implementovat řešení řízení zdroje, které poskytuje model řízení bohaté zdroj, který nezaznamenává adekvátní pomocí rozhraní API ovládacího prvku Plug-in zdroje, zvažte jako cesta k integraci balíček zdroj ovládacího prvku. To platí hlavně v případě, že by místo nahradit zdrojový balíček adaptér ovládacího prvku (která komunikuje s moduly plug-in programu zdroj ovládacího prvku a poskytuje základní zdrojového kódu uživatelského rozhraní) vlastními tak, aby bylo možné zpracovat události ovládacího prvku zdroje vlastní způsobem. Pokud již máte uspokojivé zdroj řídit uživatelského rozhraní a chcete zachovat v tomto prostředí [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], možnost řízení balíček zdroje umožňuje přesně k tomu. Zdrojový balíček ovládací prvek není obecné a je určený výhradně pro použití s [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE.  
  
 Pokud chcete implementovat řešení řízení zdroje, které poskytuje flexibilitu a bohatší kontrolu nad logiku zdroj ovládacího prvku a uživatelského rozhraní, dáte možná přednost zdroj ovládacího prvku balíček integrace trasy. Můžeš:  
  
1.  Zaregistrovat vlastní zdrojového kódu VSPackage (viz [registrace a výběr](../../extensibility/internals/registration-and-selection-source-control-vspackage.md)).  
  
2.  Nahraďte váš vlastní uživatelské rozhraní výchozí zdrojového kódu uživatelského rozhraní (viz [vlastní uživatelské rozhraní](../../extensibility/internals/custom-user-interface-source-control-vspackage.md)).  
  
3.  Zadejte glyfů chcete použít a zpracování událostí glyfy Průzkumníku řešení (najdete v části [glyfy řízení](../../extensibility/internals/glyph-control-source-control-vspackage.md)).  
  
4.  Zpracování událostí dotazu upravit a uložit dotazu (viz [dotazu upravit dotaz uložit](../../extensibility/internals/query-edit-query-save-source-control-vspackage.md)).  
  
## <a name="see-also"></a>Viz také  
 [Vytvoření ovládacího prvku zdroj modulu Plug-in](../../extensibility/internals/creating-a-source-control-plug-in.md)