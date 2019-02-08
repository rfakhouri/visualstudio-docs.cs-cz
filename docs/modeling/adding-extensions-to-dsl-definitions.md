---
title: Přidávání rozšíření do definicí DSL
ms.date: 11/04/2016
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: ec4be7c084bbcd1a73affa3035f1ef116d958c9a
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/08/2019
ms.locfileid: "55909620"
---
# <a name="add-extensions-to-dsl-definitions"></a>Přidání rozšíření do definic DSL

Rozšíření definice DSL umožňuje vytvořit balíček rozšíření jazyka specifického pro doménu (DSL). Rozšíření DSL, která je obsažena ve Visual Studio integrace rozšíření (VSIX), můžete nainstalovat na počítači uživatele stejným způsobem jako DSL. Další funkce můžete dynamicky povolené a zakázané v době běhu. DSL nemusí být vytvořené speciálně pro rozšíření a rozšíření nelze navrhovat později, nebo třetími stranami, beze změny rozšířené DSL.

Rozšíření DSL může obsahovat následující funkce:

-   Vlastnosti elementů modelu a prezentace

-   Dekoratéry pro obrazců a konektorů

-   Třídy, relace, obrazců a konektorů

-   Omezení ověření

-   Položky panelu nástrojů a karty

Uživatel rozšířené DSL můžete vytvořit a uložit model, který obsahuje instance další funkce. Model lze číst jinými uživateli, kteří nainstalovali odpovídající rozšíření. Uživatelé, kteří nejsou nainstalované rozšíření nemůže používat další funkce, ale můžete aktualizovat a uložit model bez ztráty další funkce.

[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]

## <a name="see-also"></a>Viz také

- [Související blogové příspěvky](https://blogs.msdn.microsoft.com/visualstudioalm/tag/code-index/)
