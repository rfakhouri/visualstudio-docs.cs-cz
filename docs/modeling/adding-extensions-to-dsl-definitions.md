---
title: Přidávání rozšíření do definicí DSL
ms.date: 11/04/2016
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: e9f39c45382fc55144f8200c3951fb4a229b7a43
ms.sourcegitcommit: f7c401a376ce410336846835332a693e6159c551
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/14/2019
ms.locfileid: "57867368"
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

- [Související blogové příspěvky](https://devblogs.microsoft.com/devops/the-visual-studio-modeling-sdk-is-now-available-with-visual-studio-2017/)
