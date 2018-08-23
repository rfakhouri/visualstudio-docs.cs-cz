---
title: Referenční dokumentace (zachytávání prostřednictvím kódu programu) | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ef60eb8d-1ac2-4e3a-9b4b-f6da0bdd9da8
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 70581d468c32964d7e081ec0ee4af3fe411b71b9
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42670757"
---
# <a name="reference-programmatic-capture"></a>Referenční dokumentace (zachytávání prostřednictvím kódu programu)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [referenční dokumentace (zachytávání prostřednictvím kódu programu)](https://docs.microsoft.com/visualstudio/debugger/graphics/reference-programmatic-capture).  
  
Diagnostika grafiky podporuje programovou kontrolu nad jeho zachytávání funkce zachytávání prostřednictvím kódu programu rozhraní API. Toto rozhraní API můžete přepnout přidat zprávy pro diagnostiku grafiky HUD (vedoucí nahoru zobrazení), inicializaci, vytvoření souborů protokolu grafiky a zachytit informace grafiky.  
  
## <a name="programmatic-capture-apis"></a>Rozhraní API pro zachytávání prostřednictvím kódu programu  
  
### <a name="classes"></a>Třídy  
  
|Název|Popis|  
|----------|-----------------|  
|[Třída VsgDbg](../debugger/vsgdbg-class.md)|Představuje rozhraní, přes který součást diagnostiky grafiky v aplikaci je řízen prostřednictvím kódu programu.|  
  
### <a name="preprocessor-symbols"></a>Symboly preprocesoru  
  
|Název|Popis|  
|----------|-----------------|  
|[DONT_SAVE_VSGLOG_TO_TEMP](../debugger/dont-save-vsglog-to-temp.md)|Definuje jeho přítomnost, zda soubor protokolu grafiky je uložen do adresáře dočasných souborů uživatele.|  
|[VSG_DEFAULT_RUN_FILENAME](../debugger/vsg-default-run-filename.md)|Definuje výchozí název souboru pro soubor protokolu grafiky.|  
|[VSG_NODEFAULT_INSTANCE](../debugger/vsg-nodefault-instance.md)|Definuje, zda výchozí instanci jeho přítomnost `VsgDbg` třídy je k dispozici.|  
  
## <a name="related-articles"></a>Související články  
  
|Název|Popis|  
|-----------|-----------------|  
|[Zaznamenání grafických informací](../debugger/capturing-graphics-information.md)|Ukazuje, jak zachytit informace grafiky z aplikace založené na rozhraní DirectX, aby mohli používat [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] nástrojů diagnostiky grafiky k diagnostice problémů vykreslování.|  
|[Přehled](../debugger/overview-of-visual-studio-graphics-diagnostics.md)|Ukazuje, jak Diagnostika grafiky vám může pomoci ladit chyby vykreslování her a aplikací DirectX.|



