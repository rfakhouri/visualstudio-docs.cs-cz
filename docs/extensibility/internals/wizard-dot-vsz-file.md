---
title: Průvodce (. Soubor vsz) | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- .vsz files
- vsz files
- wizards, files
ms.assetid: 72e1d0f3-eef1-455e-b803-96827f030f50
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: b4bbd69bc92ee96fcf93749aa6f700ad76ff72c8
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66309722"
---
# <a name="wizard-vsz-file"></a>Soubor průvodce (.Vsz)

Integrované vývojové prostředí (IDE) používá souborů .vsz ke spouštění průvodců. Tyto soubory .vsz obsahují informace, které prostředí IDE používá k určení, které průvodce k volání a jaké informace se mají předat do průvodce.

Soubor .vsz je verze souboru textu ve formátu .ini, který nemá žádné oddíly. Informace o známých rozhraní IDE se ukládají na začátku souboru. To poskytuje spojení mezi průvodce, který volá rozhraní IDE a parametry, které jsou v souboru .vsz předávat do integrovaného vývojového prostředí. Zbytek souboru obsahuje parametry, které jsou specifické pro průvodce a, který se má shromažďovat integrovaného vývojového prostředí a předat konkrétní průvodce.

Následující příklad ukazuje obsah souboru.

```
VSWizard 8.0
Wizard=VsWizard.CBlankSiteWizard -or- {123-1234556-123334}
Param="WIZARDNAME = Wizard One"
Param="WIZARDUI = FALSE"
```

Toto jsou částí v souboru.

|Část|Popis|
|----------|-----------------|
|VSWizard|První parametr v souboru je číslo verze formátu souboru šablony. Toto číslo verze musí být 6.0, 7.0, 7.1 nebo 8.0. Různé počty nelze spustit a způsobit chybu neplatný formát.|
|Průvodce|Toto pole obsahuje OLE ProgID průvodce, případně řetězcové vyjádření identifikátoru GUID CLSID průvodce, který je spoluvytvářen pomocí integrovaného vývojového prostředí.|
|Param|Tyto části jsou volitelné. Můžete přidat až potřebné.|

Parametry povolení souboru .vsz předávat další vlastní parametry průvodce. Každá hodnota předána jako element řetězce v poli variant průvodce. Další informace najdete v tématu [vlastní parametry](../../extensibility/internals/custom-parameters.md).

Pro přidání ID národního prostředí výchozí do souboru .vsz, zadejte `FALLBACK_LCID`= xxxx, kde xxxx je ID národního prostředí, například 1033 pro angličtinu. Když `FALLBACK_LCID` je definován parametr, Průvodce používá ID zadaného národního prostředí pro použití náhradní lokality, pokud aktuální ID nebyl nalezen.

## <a name="see-also"></a>Viz také:

- [Vlastní parametry](../../extensibility/internals/custom-parameters.md)
- [Průvodci](../../extensibility/internals/wizards.md)
- [Soubory popisu adresáře šablon (.Vsdir)](../../extensibility/internals/template-directory-description-dot-vsdir-files.md)