---
title: Moduly plug-in správy zdrojového | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- source control plug-ins, reference
ms.assetid: 964980ca-21c5-4706-8535-6ea23e1c9cc9
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: a717fdb885669ae4893dc4234c58233dec2957be
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62800144"
---
# <a name="source-control-plug-ins"></a>Moduly plug-in správy zdrojového kódu
Zdrojový ovládací prvek modulu Plug-in SDK odkaz na oddíl obsahuje kompletní rozhraní specifikace, která umožňuje systémy správy zdrojového kódu pro integraci s [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Určuje syntaxi a sémantiku různé funkce a datové typy, které modul plug-in správy zdrojového kódu musí implementovat rozhraní s [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] integrované vývojové prostředí (IDE).

## <a name="in-this-section"></a>V tomto oddílu
- [Zdroje funkcí rozhraní API ovládacího prvku modulu Plug-in](../extensibility/source-control-plug-in-api-functions.md) seznam funkcí, které je třeba implementovat modul plug-in správy zdrojového kódu, aby bylo možné v souladu s rozhraním API modulů Plug-in zdroje ovládacího prvku.

- [Zpětné volání funkce implementované integrovaným vývojovým prostředím](../extensibility/callback-functions-implemented-by-the-ide.md) popisuje funkce, které modul plug-in správy zdrojového kódu se používá k předání informací zpět do integrovaného vývojového prostředí, zatímco některé příkazy provádějí.

- [Enumerátory](../extensibility/enumerators.md) uvádí výčet datových typů v rozhraní API modulu Plug-in zdroje ovládacího prvku, které musíte znát plug-in správy zdrojových kódů.

- [Příznaky funkcí](../extensibility/capability-flags.md) popisuje `SCC_CAP_xxx` příznaky, které se označují schopnosti poskytovatele.

- [Příznaky Bitflag používané konkrétními příkazy](../extensibility/bitflags-used-by-specific-commands.md) uvádí příznaky, které jsou užitečné v kontextu konkrétní příkazy.

- [Kódy chyb](../extensibility/error-codes.md) jsou uvedeny běžné chyby hodnoty vrácené funkcí jako `SCCTRN`.

- [Řetězce používané jako klíče pro vyhledání modulu Plug-in zdrojového ovládacího prvku](../extensibility/strings-used-as-keys-for-finding-a-source-control-plug-in.md) popisuje klíče pro přístup k registru k vyhledání modulu plug-in správy zdrojového kódu.

- [MSSCCPRJ. Soubor SCC](../extensibility/mssccprj-scc-file.md) popisuje soubor na straně klienta, který obsahuje informace neprůhledné rozhraní IDE, ale modul plug-in správy zdrojového kódu, která je používaná k nalezení řešení nebo projektu ve správě verzí.

- [Osvědčené postupy pro implementaci modulu Plug-in zdrojového ovládacího prvku](../extensibility/best-practices-for-implementing-a-source-control-plug-in.md) poskytuje kolekci důležité technické připomenutí pamatovat, když implementujete rozhraní API modulu Plug-in zdroje ovládacího prvku.

- [Omezení délky řetězců](../extensibility/restrictions-on-string-lengths.md) popisuje omezení v rozhraní API modulu Plug-in zdroje ovládacího prvku na délky řetězce použité v různých funkcí.

- [Glosář](../extensibility/source-control-plug-in-glossary.md) poskytuje užitečné termíny a jejich definice pro čtení v dokumentaci sady SDK modulu Plug-in zdroje ovládacího prvku.

- [Postupy: Zapnout vypnutí upozornění kompatibility pro moduly plug-in správy zdrojových kódů](../extensibility/how-to-turn-off-compatibility-warnings-for-source-control-plug-ins.md) popisuje, jak zakázat upozornění.

## <a name="related-sections"></a>Související oddíly
- [Ukázka modulu Plug-in ovládací prvek zdroje](https://www.microsoft.com/download/details.aspx?id=55984) najdete vzorek funkce modulu plug-in správy zdrojového kódu.

- [Testovací Příručka pro moduly plug-in správy zdrojových kódů](../extensibility/internals/test-guide-for-source-control-plug-ins.md) popisuje testovací postupy související s plug-in správy zdrojových kódů.

- [Vytvoření modulu Plug-in zdrojového ovládacího prvku](../extensibility/internals/creating-a-source-control-plug-in.md) popisuje, jak vytvořit plug-in správy zdrojových kódů, který poskytuje funkce správy zdrojového kódu, zatímco používáte [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] zdrojového ovládacího prvku uživatelského rozhraní (UI).

- [Referenční dokumentace jazyka Visual Studio SDK](../extensibility/visual-studio-sdk-reference.md) zobrazí seznam referenčních témat.