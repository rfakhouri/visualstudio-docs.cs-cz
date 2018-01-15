---
title: "Přidání rozšíření do definice DSL | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: b3abe11e747db81579fb3851a1d05562d3f2fd11
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/13/2018
---
# <a name="adding-extensions-to-dsl-definitions"></a>Přidávání rozšíření do definicí DSL
Rozšíření definice DSL umožňuje vytvořit balíček rozšíření pro jazyk, specifické pro doménu (DSL). Přípony DSL, který je obsažen ve Visual Studio integrace rozšíření (VSIX), lze nainstalovat na počítači uživatele stejným způsobem jako DSL. Další funkce lze dynamicky povolit a zakázat v době běhu. DSL, linky nemusí být explicitně určen pro rozšíření a rozšíření nelze navrhnout později nebo třetích stran beze změny rozšířené DSL.  
  
 Další funkce patří:  
  
-   Vlastnosti elementů modelu a prezentace  
  
-   Dekoratéry pro konektory a obrazců  
  
-   Třídy, relace, tvarů a konektory  
  
-   Omezení ověřování  
  
-   Položky panelu nástrojů a karty  
  
 Uživatel rozšířené DSL můžete vytvořit a uložit model, který obsahuje instance další funkce, a to může být čten jiných uživatelů, kteří mají nainstalované příslušná rozšíření. Uživatelé, kteří nejsou nainstalované rozšíření nelze použít další funkce, ale můžete aktualizovat a uložit model bez ztráty dalších funkcí.  

[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]

## <a name="see-also"></a>Viz také  
 [Příspěvky blogu související](https://blogs.msdn.microsoft.com/visualstudioalm/tag/code-index/)
