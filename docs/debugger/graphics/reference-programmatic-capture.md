---
title: Referenční dokumentace (zachytávání prostřednictvím kódu programu) | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: ef60eb8d-1ac2-4e3a-9b4b-f6da0bdd9da8
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 826b399aa0ad0b5a45bc6fd80eb73b555cb3f01c
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53836344"
---
# <a name="reference-programmatic-capture"></a>Referenční dokumentace (zachytávání prostřednictvím kódu programu)
Diagnostika grafiky podporuje programovou kontrolu nad jeho zachytávání funkce zachytávání prostřednictvím kódu programu rozhraní API. Toto rozhraní API můžete přepnout přidat zprávy pro diagnostiku grafiky HUD (vedoucí nahoru zobrazení), inicializaci, vytvoření souborů protokolu grafiky a zachytit informace grafiky.  

## <a name="programmatic-capture-apis"></a>Rozhraní API pro zachytávání prostřednictvím kódu programu  

### <a name="classes"></a>Třídy  

|Název|Popis|  
|----------|-----------------|  
|[Třída VsgDbg](vsgdbg-class.md)|Představuje rozhraní, přes který součást diagnostiky grafiky v aplikaci je řízen prostřednictvím kódu programu.|  

### <a name="preprocessor-symbols"></a>Symboly preprocesoru  

|Název|Popis|  
|----------|-----------------|  
|[DONT_SAVE_VSGLOG_TO_TEMP](dont-save-vsglog-to-temp.md)|Definuje jeho přítomnost, zda soubor protokolu grafiky je uložen do adresáře dočasných souborů uživatele.|  
|[VSG_DEFAULT_RUN_FILENAME](vsg-default-run-filename.md)|Definuje výchozí název souboru pro soubor protokolu grafiky.|  
|[VSG_NODEFAULT_INSTANCE](vsg-nodefault-instance.md)|Definuje, zda výchozí instanci jeho přítomnost `VsgDbg` třídy je k dispozici.|  

## <a name="related-articles"></a>Související články  

| Název | Popis |
| - | - |
| [Zaznamenání grafických informací](capturing-graphics-information.md) | Ukazuje, jak zachytit informace grafiky z aplikace založené na rozhraní DirectX, aby mohli používat [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] nástrojů diagnostiky grafiky k diagnostice problémů vykreslování. |
| [Přehled](overview-of-visual-studio-graphics-diagnostics.md) | Ukazuje, jak Diagnostika grafiky vám může pomoci ladit chyby vykreslování her a aplikací DirectX. |
