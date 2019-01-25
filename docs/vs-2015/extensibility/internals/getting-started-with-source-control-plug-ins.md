---
title: Začínáme s plug-in zdroje ovládacího prvku | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- source control plug-ins, getting started
- getting started, source control plug-ins
ms.assetid: 46ac1f9f-4ecc-4a72-88d3-4c7e1647e1cb
caps.latest.revision: 22
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 85aa5727f252ad75c45064d7b885e3d282da36a4
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54782721"
---
# <a name="getting-started-with-source-control-plug-ins"></a>Začínáme s moduly plug-in správy zdrojového kódu
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Chcete-li vytvořit modul plug-in správy zdrojového kódu, musíte vytvořit knihovnu DLL, která implementuje funkce definované v rozhraní API modulu Plug-in zdroje ovládacího prvku a následně registrace knihovny DLL s [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] aby byl k dispozici pro použití v správy verze zdrojového kódu.  
  
 Tři verze rozhraní API modulu Plug-in zdroje ovládacího prvku (verze 1.1, 1.2 a 1.3) jsou k dispozici pro ovládací prvek moduly plug-in zdrojového kódu. Rozhraní API modulu Plug-in zdroje ovládacího prvku zdokumentované tady je verze 1.3. Jejím účelem je plně kompatibilní s ovládací prvek moduly plug-in zdrojového kódu podporující verze 1.1 a 1.2. [Co je nového ve verzi 1.3 zdroj ovládacího prvku modulu Plug-in API](../../extensibility/internals/what-s-new-in-the-source-control-plug-in-api-version-1-3.md) část podrobně popisuje nové funkce podporované v nejnovější verzi rozhraní API modulu Plug-in zdroje ovládacího prvku.  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Postupy: Instalace modulu Plug-in správy zdrojového kódu](../../extensibility/internals/how-to-install-a-source-control-plug-in.md)  
 Popisuje, jak vytvořit položky registru, které jsou nutné k modulu plug-in správy zdrojového kódu knihovny DLL.  
  
 [Co je nového v rozhraní API modulu plug-in správy zdrojového kódu ve verzi 1.3](../../extensibility/internals/what-s-new-in-the-source-control-plug-in-api-version-1-3.md)  
 Poskytuje stručný přehled o změny, které byly provedeny API modulu Plug-in zdroje ovládacího prvku ve verzi 1.3.  
  
 [Co je nového v rozhraní API modulu plug-in správy zdrojového kódu ve verzi 1.2](../../extensibility/internals/what-s-new-in-the-source-control-plug-in-api-version-1-2.md)  
 Poskytuje stručný přehled o změny, které byly provedeny u rozhraní API pro modul Plug-in zdroje ovládacího prvku ve verzi 1.2.  
  
## <a name="related-sections"></a>Související oddíly  
 [Moduly plug-in správy zdrojového kódu](../../extensibility/source-control-plug-ins.md)  
 Obsahuje úplný seznam všech prvků v rozhraní API modulu Plug-in zdroje ovládacího prvku.  
  
 [Vytvoření modulu plug-in správy zdrojového kódu](../../extensibility/internals/creating-a-source-control-plug-in.md)  
 Definuje ovládací prvek modulu Plug-in Source sad SDK a popisuje zahrnuté prostředky.
