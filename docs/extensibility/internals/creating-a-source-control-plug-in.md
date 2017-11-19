---
title: "Vytvoření ovládacího prvku zdroj modulu Plug-in | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- plug-ins, source control
- source control plug-ins
- source control [Visual Studio SDK], plug-ins
ms.assetid: c7e69fa4-150e-469a-a6fc-fa1260bdbb07
caps.latest.revision: "18"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: e376ced68301abae6090a87114e2178c0adc28cf
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="creating-a-source-control-plug-in"></a>Vytvoření ovládacího prvku zdroj modulu Plug-in
Visual Studio SDK poskytuje prostředky, které vám umožní přidat možnost Zdroj ovládacího prvku [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] integrované vývojové prostředí (IDE). Umožňuje vám použít jakékoli knihovnu DLL modulu plug-in, který je v souladu s rozhraním API Plug-in Zdroj ovládacího prvku uvedených v této dokumentaci.  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Začínáme](../../extensibility/internals/getting-started-with-source-control-plug-ins.md)  
 Popisuje postup instalace modulu plug-in Správa zdrojového kódu a zvýrazňuje aktuálně k dispozici verze rozhraní API modulu Plugin zdroj ovládacího prvku.  
  
 [Architektura](../../extensibility/internals/source-control-plug-in-architecture.md)  
 Používá diagram architektury vysvětlit, integrace modulu plug-in se správa zdrojového kódu [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE.  
  
 [Příručka pro testovací modulů plug-in programu zdroj ovládacího prvku](../../extensibility/internals/test-guide-for-source-control-plug-ins.md)  
 Poskytuje pokyny o tom, jak otestovat instalaci a používání modulu plug-in Správa zdrojového kódu.  
  
## <a name="related-sections"></a>Související oddíly  
 [Vytvoření ovládacího prvku VSPackage zdroje](../../extensibility/internals/creating-a-source-control-vspackage.md)  
 Popisuje postup vytvoření zdrojového kódu VSPackage, který není pouze poskytuje funkce správy zdrojového ale nahradí [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] zdroj ovládacího prvku uživatelského rozhraní.  
  
 [Moduly plug-in programu zdroj ovládacího prvku](../../extensibility/source-control-plug-ins.md)  
 Obsahuje úplný seznam všech elementů v rozhraní API ovládacího prvku Plug-in zdroje.  
  
 [Správa zdrojového kódu](../../extensibility/internals/source-control.md)  
 Popisuje možnosti pro implementaci správy zdrojového kódu jako integrovaná funkce [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].