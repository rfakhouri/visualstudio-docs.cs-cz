---
title: "Začínáme s moduly plug-in programu zdroj ovládacího prvku | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- source control plug-ins, getting started
- getting started, source control plug-ins
ms.assetid: 46ac1f9f-4ecc-4a72-88d3-4c7e1647e1cb
caps.latest.revision: "21"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 3ccbc7536a899226b7f2d9433b6c451df33bbde5
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="getting-started-with-source-control-plug-ins"></a>Začínáme s moduly plug-in programu zdroj ovládacího prvku
K vytvoření modulu Plugin pro ovládací prvek zdroje, musíte vytvořit knihovnu DLL, která implementuje funkce definované v rozhraní API modulu Plugin zdroj ovládacího prvku a potom registrace knihovny DLL s [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] aby byla k dispozici pro použití ve správě zdrojového kódu verzí.  
  
 Tři verze rozhraní API modulu Plugin zdroj ovládacího prvku (verze 1.1, 1.2 a 1.3) jsou k dispozici pro moduly plug-in programu zdroj ovládacího prvku. Rozhraní API modulu Plugin zdroj ovládacího prvku tady popisujeme je verze 1.3. Byla navržená tak, aby se plně kompatibilní se zdroj ovládacího prvku zásuvné moduly podpora verze 1.1 a 1.2. [Co je nového ve verzi 1.3 zdroj ovládacího prvku Plug-in rozhraní API](../../extensibility/internals/what-s-new-in-the-source-control-plug-in-api-version-1-3.md) část Podrobnosti o nové funkce podporované v nejnovější verzi rozhraní API ovládacího prvku Plug-in zdroje.  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Postupy: Instalace modulu Plug-in Správa zdrojového kódu](../../extensibility/internals/how-to-install-a-source-control-plug-in.md)  
 Popisuje postup vytvoření položky registru, které jsou nutné k ve správě zdrojového kódu knihovnu DLL modulu plug-in.  
  
 [Co je nového v zdroj ovládacího prvku modulu Plug-in verze rozhraní API 1.3](../../extensibility/internals/what-s-new-in-the-source-control-plug-in-api-version-1-3.md)  
 Poskytuje stručný přehled změn, které byly provedeny řízení zdroj Plug-in rozhraní API ve verzi 1.3.  
  
 [Co je nového v zdroj ovládacího prvku modulu Plug-in rozhraní API verze 1.2](../../extensibility/internals/what-s-new-in-the-source-control-plug-in-api-version-1-2.md)  
 Poskytuje stručný přehled změn, které byly provedeny řízení zdroj Plug-in rozhraní API ve verzi 1.2.  
  
## <a name="related-sections"></a>Související oddíly  
 [Moduly plug-in programu zdroj ovládacího prvku](../../extensibility/source-control-plug-ins.md)  
 Obsahuje úplný seznam všech elementů v rozhraní API ovládacího prvku Plug-in zdroje.  
  
 [Vytvoření ovládacího prvku zdroj modulu Plug-in](../../extensibility/internals/creating-a-source-control-plug-in.md)  
 Definuje sadu SDK Plug-in Zdroj ovládacího prvku a popisuje zahrnuté prostředky.