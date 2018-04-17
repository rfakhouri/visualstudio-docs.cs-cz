---
title: Vytvoření ovládacího prvku zdroj modulu Plug-in | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- plug-ins, source control
- source control plug-ins
- source control [Visual Studio SDK], plug-ins
ms.assetid: c7e69fa4-150e-469a-a6fc-fa1260bdbb07
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 04c6125004aaf2740b54acdce91bef032647c6e5
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="creating-a-source-control-plug-in"></a>Vytvoření ovládacího prvku zdroj modulu Plug-in
Visual Studio SDK poskytuje prostředky, které vám umožní přidat možnost Zdroj ovládacího prvku [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] integrované vývojové prostředí (IDE). Umožňuje vám použít jakékoli knihovnu DLL modulu plug-in, který je v souladu s rozhraním API Plug-in Zdroj ovládacího prvku uvedených v této dokumentaci.  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Začínáme](../../extensibility/internals/getting-started-with-source-control-plug-ins.md)  
 Popisuje postup instalace modulu plug-in Správa zdrojového kódu a zvýrazňuje aktuálně k dispozici verze rozhraní API modulu Plugin zdroj ovládacího prvku.  
  
 [Architektura](../../extensibility/internals/source-control-plug-in-architecture.md)  
 Používá diagram architektury vysvětlit, integrace modulu plug-in se správa zdrojového kódu [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE.  
  
 [Testovací příručka pro moduly plug-in správy zdrojového kódu](../../extensibility/internals/test-guide-for-source-control-plug-ins.md)  
 Poskytuje pokyny o tom, jak otestovat instalaci a používání modulu plug-in Správa zdrojového kódu.  
  
## <a name="related-sections"></a>Související oddíly  
 [Vytvoření balíčku VSPackage správy zdrojového kódu](../../extensibility/internals/creating-a-source-control-vspackage.md)  
 Popisuje postup vytvoření zdrojového kódu VSPackage, který není pouze poskytuje funkce správy zdrojového ale nahradí [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] zdroj ovládacího prvku uživatelského rozhraní.  
  
 [Moduly plug-in správy zdrojového kódu](../../extensibility/source-control-plug-ins.md)  
 Obsahuje úplný seznam všech elementů v rozhraní API ovládacího prvku Plug-in zdroje.  
  
 [Správa zdrojového kódu](../../extensibility/internals/source-control.md)  
 Popisuje možnosti pro implementaci správy zdrojového kódu jako integrovaná funkce [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].