---
title: 'Postupy: Export shaderu | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-designers
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0bd48bf4-9792-4456-a545-e462a2be668d
caps.latest.revision: "11"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: ea578a020b4e60c3a2ff11af5d78570d636d822f
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-export-a-shader"></a>Postupy: Exportování shaderu
Tento dokument ukazuje, jak používat návrháře shaderu export shaderu směrované grafu shaderu jazyk (DGSL), aby ho můžete používat ve vaší aplikaci.  
  
 Tento dokument ukazuje této aktivity:  
  
-   Export shaderu  
  
## <a name="exporting-a-shader"></a>Export shaderu  
 Po vytvoření shaderu pomocí návrháře shaderu a před použitím v aplikaci, je nutné ho exportovat ve formátu, který funguje s technologií vaší grafické rozhraní API. Je možné exportovat shaderu různými způsoby pro různé účely.  
  
#### <a name="to-export-a-shader"></a>Chcete-li exportovat shaderu  
  
1.  V [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], otevřete **Visual shaderu grafu (.dgsl)** souboru.  
  
     Pokud nemáte **Visual shaderu grafu (.dgsl)** soubor otevřít, vytvořte ho, jak je popsáno v [postupy: vytvoření základní shaderu barva](../designers/how-to-create-a-basic-color-shader.md).  
  
2.  Na **shaderu Návrhář** nástrojů vyberte **Upřesnit**, **exportovat**, **exportovat jako**. **Exportovat shaderu** se zobrazí dialogové okno.  
  
3.  V **uložit jako typ** rozevíracího seznamu vyberte formát, který chcete exportovat.  
  
     Zde jsou formáty, které je možné:  
  
     **Shaderu HLSL pixelů (\*.hlsl)**  
     Exportuje shaderu jako vysokou úroveň shaderu jazyk (HLSL) zdrojového kódu. Tato možnost umožňuje později upravit shaderu i po jeho nasazení v aplikaci. To může být snazší ladit a oprava kód podle problémy koncového uživatele, ale také umožňuje jednodušší pro uživatele k úpravě vaší shaderu nežádoucí způsoby – například k získání nekalé výhodu v konkurenčním prostředí hru. Čas načítání shaderu také může zvýšit.  
  
     **Kompilované shaderu pixelů (\*.cso)**  
     Exportuje shaderu jako bajtového HLSL kódu. Tato možnost díky je možné později změnit shaderu i po jeho nasazení v aplikaci. To může být snazší ladit a oprava kód podle problémy koncového uživatele, ale shaderu je předem kompilovaném, a proto ho nedojde režijní náklady na další runtime při načtení shaderu aplikací. Dostatečně zkušený mohou uživatelé stále změnit shaderu nežádoucím způsobem, ale kompilování shaderu to provádí podstatně obtížnější.  
  
     **Hlavička C++ (\*.h)**  
     Exportuje shaderu jako hlavičku stylu jazyka C, která definuje bajtové pole obsahující bajtového HLSL kódu. Tato možnost může být zabírá více času, ladit a oprava kód podle problémy koncového uživatele, protože aplikace musí zopakovat pro testování opravu. Ale vzhledem k tomu, že tato možnost provede obtížné, i když není možné změnit shaderu po jeho nasazení v aplikaci, představuje většina potíže s uživateli, který chce změnit shaderu nežádoucí způsoby.  
  
4.  V **název souboru** – pole se seznamem, zadejte název pro exportovaný shaderu a potom zvolte **Uložit** tlačítko.  
  
## <a name="see-also"></a>Viz také  
 [Postupy: vytvoření základní barva shaderu](../designers/how-to-create-a-basic-color-shader.md)   
 [Návrhář shaderu](../designers/shader-designer.md)