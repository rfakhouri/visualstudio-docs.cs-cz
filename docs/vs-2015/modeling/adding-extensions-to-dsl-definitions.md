---
title: Přidávání rozšíření do definicí DSL | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: conceptual
ms.assetid: 07e133be-92ab-4936-a02b-45d2012bd0a6
caps.latest.revision: 8
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: bd45a2345e6e5b28b74cb27fac226514c3f92a04
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68159082"
---
# <a name="adding-extensions-to-dsl-definitions"></a>Přidávání rozšíření do definicí DSL
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Rozšíření definice DSL umožňuje vytvořit balíček rozšíření jazyka specifického pro doménu (DSL). Rozšíření DSL, která je obsažena ve Visual Studio integrace rozšíření (VSIX), můžete nainstalovat na počítači uživatele stejným způsobem jako DSL. Další funkce můžete dynamicky povolené a zakázané v době běhu. DSL nemusí být vytvořené speciálně pro rozšíření a rozšíření nelze navrhovat později nebo třetími stranami beze změny rozšířené DSL.  
  
 Další funkce patří:  
  
- Vlastnosti elementů modelu a prezentace  
  
- Dekoratéry pro obrazců a konektorů  
  
- Třídy, relace, obrazců a konektorů  
  
- Omezení ověření  
  
- Položky panelu nástrojů a karty  
  
  Uživatel rozšířené DSL můžete vytvořit a uložit model, který obsahuje instance další funkce a dají se číst jinými uživateli, kteří nainstalovali odpovídající rozšíření. Uživatelé, kteří nejsou nainstalované rozšíření nemůže používat další funkce, ale můžete aktualizovat a uložit model bez ztráty další funkce.  
  
  Ukázkový kód a další informace o této funkci najdete v tématu [Visual Studio Visualization and Modeling SDK](http://go.microsoft.com/fwlink/?LinkID=186128) webu.  
  
## <a name="see-also"></a>Viz také  
 [Visual Studio Visualization and Modeling SDK](http://go.microsoft.com/fwlink/?LinkID=186128)
