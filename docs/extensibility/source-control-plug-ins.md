---
title: "Zdroj ovládacího prvku moduly plug-in | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- source control plug-ins, reference
ms.assetid: 964980ca-21c5-4706-8535-6ea23e1c9cc9
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 4f05a0b41a46adfee827f9cc1a36ab7bdd44cd0a
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="source-control-plug-ins"></a>Moduly plug-in programu zdroj ovládacího prvku
Odkaz na zdroj ovládacího prvku Plug-in SDK obsahuje specifikace dokončení rozhraní, která umožňuje integraci s zdrojových systémů řízení [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Určuje syntaxi a sémantiku různé typy funkcí a dat, které se správa zdrojového kódu modul plug-in musí implementovat rozhraní s [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] integrované vývojové prostředí (IDE).  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Funkce modulu plug-in správy zdrojového kódu v rozhraní API](../extensibility/source-control-plug-in-api-functions.md)  
 Obsahuje seznam funkcí, které musí být implementována pomocí modulu plug-in zdrojového kódu pro dosažení souladu s rozhraním API Plug-in Zdroj ovládacího prvku.  
  
 [Funkce zpětného volání implementované integrovaným vývojovým prostředím](../extensibility/callback-functions-implemented-by-the-ide.md)  
 Popisuje funkce, které používá modul plug-in správy zdroje předávat informace zpět do prostředí IDE při provedení určité příkazy.  
  
 [Enumerátory](../extensibility/enumerators.md)  
 Uvádí enumerátor datových typů v rozhraní API Plug-in ovládací prvek zdroje, musíte znát modulu plug-in zdrojového kódu.  
  
 [Příznaky funkcí](../extensibility/capability-flags.md)  
 Popisuje `SCC_CAP_xxx` příznaky, které se označují možnosti zprostředkovatele.  
  
 [Příznaky bitflag používané konkrétními příkazy](../extensibility/bitflags-used-by-specific-commands.md)  
 Uvádí příznaky, které jsou užitečné v rámci konkrétní příkazy.  
  
 [Chybové kódy](../extensibility/error-codes.md)  
 Jsou uvedeny běžné chyby hodnoty vrácené funkcí jako `SCCTRN`.  
  
 [Řetězce, které slouží jako klíče pro vyhledání modulu plug-in pro správu zdrojového kódu](../extensibility/strings-used-as-keys-for-finding-a-source-control-plug-in.md)  
 Popisuje klíče pro přístup k registru k vyhledání modulu plug-in zdrojového kódu.  
  
 [Soubor MSSCCPRJ.SCC](../extensibility/mssccprj-scc-file.md)  
 Popisuje klienta soubor obsahující informace neprůhledného IDE, ale modul plug-in zdrojového kódu, je používána k vyhledání řešení nebo projektu ve správě verzí.  
  
 [Osvědčené postupy pro implementaci modulu plug-in zdrojového kódu](../extensibility/best-practices-for-implementing-a-source-control-plug-in.md)  
 Poskytuje kolekci důležité technické připomenutí pamatovat při implementaci rozhraní API ovládacího prvku Plug-in zdroje.  
  
 [Omezení délky řetězců](../extensibility/restrictions-on-string-lengths.md)  
 Popisuje omezení v rozhraní API modulu Plugin zdroj ovládacího prvku na délky řetězce použité v různých funkcí.  
  
 [Glosář](../extensibility/source-control-plug-in-glossary.md)  
 Poskytuje užitečné podmínek a jejich definice pro čtení v dokumentaci zdroj ovládacího prvku Plug-in SDK.  
  
 [Postupy: Vypnutí upozornění kompatibility pro moduly plug-in zdroje ovládacího prvku](../extensibility/how-to-turn-off-compatibility-warnings-for-source-control-plug-ins.md)  
 Popisuje, jak zakázat upozornění.  
  
## <a name="related-sections"></a>Související oddíly  
 [Ukázka modulu Plug-in Zdroj ovládacího prvku](http://msdn.microsoft.com/en-us/61de7d2b-71db-451e-8e3e-d41b11c7a4ca)  
 Ukázka modulu plug-in funkce správy zdrojového poskytuje.  
  
 [Testovací příručka pro moduly plug-in správy zdrojového kódu](../extensibility/internals/test-guide-for-source-control-plug-ins.md)  
 Popisuje testování postupy související s ovládacím prvkem zdroje modulu plug-in.  
  
 [Vytvoření modulu plug-in správy zdrojového kódu](../extensibility/internals/creating-a-source-control-plug-in.md)  
 Popisuje, jak vytvořit zdroj ovládací prvek modul plug-in, který poskytuje funkce správy zdrojového při používání [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] zdroj ovládacího prvku uživatelského rozhraní (UI).  
  
 [Referenční dokumentace sady Visual Studio SDK](../extensibility/visual-studio-sdk-reference.md)  
 Zobrazí seznam referenční témata.