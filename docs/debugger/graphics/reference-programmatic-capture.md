---
title: Referenční dokumentace (zachytávání prostřednictvím kódu programu) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: ef60eb8d-1ac2-4e3a-9b4b-f6da0bdd9da8
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: dd6ea361d0cec07e3f1fe1a3d5b6771ec7fcb5d6
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/18/2018
ms.locfileid: "31474385"
---
# <a name="reference-programmatic-capture"></a>Referenční dokumentace (zachytávání prostřednictvím kódu programu)
Diagnostika grafiky podporuje programovou kontrolu nad jeho zachycení funkce prostřednictvím zachytávání prostřednictvím kódu programu rozhraní API. Toto rozhraní API slouží k přepnutí a taky přidat zprávy do diagnostiky grafiky HUD (zobrazení Head-Up), inicializovat a vytvořit grafiky soubory protokolu a zaznamenání grafických informací.  
  
## <a name="programmatic-capture-apis"></a>Rozhraní API pro zachytávání prostřednictvím kódu programu  
  
### <a name="classes"></a>Třídy  
  
|Název|Popis|  
|----------|-----------------|  
|[Třída VsgDbg](vsgdbg-class.md)|Představuje rozhraní, přes který se v aplikaci součást diagnostiky grafiky řídí prostřednictvím kódu programu.|  
  
### <a name="preprocessor-symbols"></a>Symboly preprocesoru  
  
|Název|Popis|  
|----------|-----------------|  
|[DONT_SAVE_VSGLOG_TO_TEMP](dont-save-vsglog-to-temp.md)|Podle jeho přítomnosti definuje, zda soubor protokolu grafika je uložena do adresáře uživatele dočasné soubory.|  
|[VSG_DEFAULT_RUN_FILENAME](vsg-default-run-filename.md)|Definuje výchozí název souboru grafického souboru protokolu.|  
|[VSG_NODEFAULT_INSTANCE](vsg-nodefault-instance.md)|Definuje podle jeho přítomnosti zda výchozí instanci `VsgDbg` třída je k dispozici.|  
  
## <a name="related-articles"></a>Související články  
  
|Název|Popis|  
|-----------|-----------------|  
|[Zaznamenání grafických informací](capturing-graphics-information.md)|Ukazuje, jak k zaznamenání grafických informací z aplikace založené na rozhraní DirectX tak, aby můžete použít [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] nástroje diagnostiky grafiky k diagnostikování problémů vykreslování.|  
|[Přehled](overview-of-visual-studio-graphics-diagnostics.md)|Ukazuje, jak diagnostiky grafiky můžete ladění chyb při vykreslování v DirectX hry a aplikace.|