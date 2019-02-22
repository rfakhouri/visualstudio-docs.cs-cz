---
title: Funkce zpětného volání implementované integrovaným vývojovým prostředím | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- source control plug-ins, callback functions
- callback functions, source control plug-ins
ms.assetid: 4a8833f0-6ac0-4ea7-9400-8275aa991468
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: fc3b4423b54975c773de743b093f882f1fd9c42c
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56697556"
---
# <a name="callback-functions-implemented-by-the-ide"></a>Funkce zpětného volání implementované integrovaným vývojovým prostředím
Aby integrace s integrované vývojové prostředí (IDE) jako bezproblémové nejrychleji a poskytovat jednotné koncových uživatelů, modul plug-in správy zdrojového kódu můžete použít funkce zpětného volání implementované integrovaným vývojovým prostředím. Modul plug-in může volat tyto funkce ve vhodných chvílích při operaci správy zdrojových kódů k předávání informací do integrovaného vývojového prostředí; integrované vývojové prostředí můžete tyto informace zobrazit jako vložené prvky v jeho nativním uživatelským rozhraním. Uživatel má méně fragmentované prostředí v tomto scénáři než hodnotě modulu plug-in použijí své vlastní uživatelské rozhraní.

 Požadovaný hlavičkový soubor je *scc.h*. Výchozí umístění je *\Program Files\VSIP 8.0\EnvSDK\common\inc\\*. Je také ve složce VSIP, který má modul plug-in Ukázka ovládacího prvku zdroje na *\Program Files\VSIP 8.0\MSSCCI\\*.

## <a name="in-this-section"></a>V tomto oddílu
- [LPTEXTOUTPROC](../extensibility/lptextoutproc.md) popisuje funkce zpětného volání, který používá [sccopenproject –](../extensibility/sccopenproject-function.md) pro zobrazení zpráv ze správy zdrojového kódu modulu plug-in pomocí integrovaného vývojového prostředí.

- [POPLISTFUNC](../extensibility/poplistfunc.md) popisuje funkce zpětného volání, který používá [sccpopulatelist –](../extensibility/sccpopulatelist-function.md) Při integrovaném vývojovém prostředí nemá úplný přístup k informacím, které je k dispozici pouze pro modul plug-in, jako je úplný seznam správy zdrojového kódu soubory pod správu verzí.

- [QUERYCHANGESFUNC](../extensibility/querychangesfunc.md) popisuje funkce zpětného volání používané [sccquerychanges –](../extensibility/sccquerychanges-function.md) operace.

- [POPDIRLISTFUNC](../extensibility/popdirlistfunc.md) popisuje funkce zpětného volání používané [sccpopulatedirlist –](../extensibility/sccpopulatedirlist-function.md) operace.

- [OPTNAMECHANGEPFN](../extensibility/optnamechangepfn.md) popisuje nastavení voláním funkce zpětného volání [sccsetoption –](../extensibility/sccsetoption-function.md) , která umožňuje komunikovat, název změny zpět do integrovaného vývojového prostředí modulu plug-in správy zdrojového kódu.

## <a name="related-sections"></a>Související oddíly
- [Sccopenproject –](../extensibility/sccopenproject-function.md) otevře projekt.

- [Sccpopulatelist –](../extensibility/sccpopulatelist-function.md) zkontroluje seznam souborů pro jejich aktuální stav. Kromě toho používá `pfnPopulate` funkce oznámit volajícímu, soubor neodpovídá kritériím pro `nCommand`.

- [Sccpopulatedirlist –](../extensibility/sccpopulatedirlist-function.md) zkontroluje seznam adresářů a souborů v projektu nebo v projektech, které jsou pod správou zdrojových kódů. Každý název adresáře a souboru nalezena je předán funkci zpětného volání.

- [Sccquerychanges –](../extensibility/sccquerychanges-function.md) prozkoumá změn názvů, které byly provedeny seznam souborů. Každý název souboru je předán funkci zpětného volání společně s jeho změna stavu.

- [Sccsetoption –](../extensibility/sccsetoption-function.md) nastaví širokou škálu možností. Jednotlivé možnosti začíná `SCC_OPT_xxx` a má vlastní definované sady hodnot.

- [Moduly plug-in správy zdrojového](../extensibility/source-control-plug-ins.md) popisuje obsah části reference sady SDK modulu Plug-in zdroje ovládacího prvku.