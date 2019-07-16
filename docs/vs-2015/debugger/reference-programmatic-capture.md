---
title: Referenční dokumentace (zachytávání prostřednictvím kódu programu) | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
ms.assetid: ef60eb8d-1ac2-4e3a-9b4b-f6da0bdd9da8
caps.latest.revision: 8
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 8cebeb7eb651c11b5f560b981df30213fc726c66
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68162264"
---
# <a name="reference-programmatic-capture"></a>Referenční dokumentace (zachytávání prostřednictvím kódu programu)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Diagnostika grafiky podporuje programovou kontrolu nad jeho zachytávání funkce zachytávání prostřednictvím kódu programu rozhraní API. Toto rozhraní API můžete přepnout přidat zprávy pro diagnostiku grafiky HUD (vedoucí nahoru zobrazení), inicializaci, vytvoření souborů protokolu grafiky a zachytit informace grafiky.  
  
## <a name="programmatic-capture-apis"></a>Rozhraní API pro zachytávání prostřednictvím kódu programu  
  
### <a name="classes"></a>Třídy  
  
|Name|Popis|  
|----------|-----------------|  
|[Třída VsgDbg](../debugger/vsgdbg-class.md)|Představuje rozhraní, přes který součást diagnostiky grafiky v aplikaci je řízen prostřednictvím kódu programu.|  
  
### <a name="preprocessor-symbols"></a>Symboly preprocesoru  
  
|Name|Popis|  
|----------|-----------------|  
|[DONT_SAVE_VSGLOG_TO_TEMP](../debugger/dont-save-vsglog-to-temp.md)|Definuje jeho přítomnost, zda soubor protokolu grafiky je uložen do adresáře dočasných souborů uživatele.|  
|[VSG_DEFAULT_RUN_FILENAME](../debugger/vsg-default-run-filename.md)|Definuje výchozí název souboru pro soubor protokolu grafiky.|  
|[VSG_NODEFAULT_INSTANCE](../debugger/vsg-nodefault-instance.md)|Definuje, zda výchozí instanci jeho přítomnost `VsgDbg` třídy je k dispozici.|  
  
## <a name="related-articles"></a>Související články  
  
|Název|Popis|  
|-----------|-----------------|  
|[Zaznamenání grafických informací](../debugger/capturing-graphics-information.md)|Ukazuje, jak zachytit informace grafiky z aplikace založené na rozhraní DirectX, aby mohli používat [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] nástrojů diagnostiky grafiky k diagnostice problémů vykreslování.|  
|[Přehled](../debugger/overview-of-visual-studio-graphics-diagnostics.md)|Ukazuje, jak Diagnostika grafiky vám může pomoci ladit chyby vykreslování her a aplikací DirectX.|
