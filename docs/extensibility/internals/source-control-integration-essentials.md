---
title: Zdroj ovládacího prvku integrace Essentials | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- Source Control Integration, essentials
- Source Control Integration,overview
- essentials, Source Control Integration
ms.assetid: 442057cb-fd54-4283-96f8-2f6dc8bf2de7
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 0c3e93eb86fdc252f162331033207db5bdaa1569
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="source-control-integration-essentials"></a>Zdroj ovládacího prvku integrace Essentials
[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] podporuje dva typy integrace ovládacích prvků zdrojového: ovládací prvek zdroje modul plug-in, poskytuje základní funkce a je sestaven pomocí rozhraní API modulu Plugin zdroj ovládacího prvku (dříve označované jako rozhraní API MSSCCI) a integrace řešení řízení na základě VSPackage zdroje, poskytuje robustnější funkce.  
  
## <a name="source-control-plug-in"></a>Modul Plug-in správy zdrojového kódu  
 Plug-in řízení zdroj je zapsána jako knihovny DLL, která implementuje rozhraní API ovládacího prvku Plug-in zdroje. Registrace a zdroj funkce integrace ovládací prvek je zajišťováno prostřednictvím rozhraní API. Tento přístup je jednodušší než Správa zdrojového kódu VSPackage implementace a používá [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] uživatelské rozhraní (UI) pro většinu operací řízení zdroje.  
  
 K implementaci modulu plug-in pomocí rozhraní API ovládacího prvku Plug-in Zdroj Správa zdrojového kódu, postupujte takto:  
  
1.  Vytvoření knihovny DLL, která implementuje funkce, zadaný v [moduly plug-in správy zdrojového kódu](../../extensibility/source-control-plug-ins.md).  
  
2.  Zaregistruje knihovnu DLL tak, že položky odpovídající registru, jak je popsáno v [postupy: Instalace modulu Plugin zdroj ovládacího prvku](../../extensibility/internals/how-to-install-a-source-control-plug-in.md).  
  
3.  Vytvořit pomocné rutiny uživatelského rozhraní a zobrazit ji po zobrazení výzvy zdrojový balíček adaptér ovládacího prvku ( [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] komponenty, která zpracovává zdroje ovládací prvek funkce prostřednictvím modulů plug-in programu zdroj ovládacího prvku).  
  
 Další informace najdete v tématu [vytvoření modulu Plugin zdroj ovládacího prvku](../../extensibility/internals/creating-a-source-control-plug-in.md).  
  
## <a name="source-control-vspackage"></a>VSPackage zdroj ovládacího prvku  
 Správa zdrojového kódu VSPackage implementace umožňuje vyvíjet vlastní náhradní server pro [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] zdroj ovládacího prvku uživatelského rozhraní. Tento přístup poskytuje úplnou kontrolu nad integrace ovládacích prvků zdrojového, ale vyžaduje, abyste zadejte prvky uživatelského rozhraní a implementovat rozhraní pro řízení zdroje, které by se jinak uvedených v části modulu plug-in přístup.  
  
 Chcete-li implementovat VSPackage Správa zdrojového kódu, postupujte takto:  
  
1.  Vytvořit a registrovat vlastní zdrojového kódu VSPackage, jak je popsáno v [registrace a výběr](../../extensibility/internals/registration-and-selection-source-control-vspackage.md).  
  
2.  Výchozí zdrojového kódu uživatelského rozhraní nahraďte váš vlastní uživatelské rozhraní. V tématu [vlastní uživatelské rozhraní](../../extensibility/internals/custom-user-interface-source-control-vspackage.md).  
  
3.  Zadejte glyfů chcete použít a zpracování **Průzkumníku řešení** glyfy události. V tématu [glyfy řízení](../../extensibility/internals/glyph-control-source-control-vspackage.md).  
  
4.  Zpracování událostí dotazu upravit a uložit dotazu, jak je znázorněno v [dotazu upravit dotaz uložit](../../extensibility/internals/query-edit-query-save-source-control-vspackage.md).  
  
 Další informace najdete v tématu [vytváření VSPackage zdroj ovládacího prvku](../../extensibility/internals/creating-a-source-control-vspackage.md).  
  
## <a name="see-also"></a>Viz také  
 [Přehled](../../extensibility/internals/source-control-integration-overview.md)   
 [Vytvoření ovládacího prvku zdroj modulu Plug-in](../../extensibility/internals/creating-a-source-control-plug-in.md)   
 [Vytvoření balíčku VSPackage správy zdrojového kódu](../../extensibility/internals/creating-a-source-control-vspackage.md)