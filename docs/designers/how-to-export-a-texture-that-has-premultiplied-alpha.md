---
title: "Postupy: Export Texture, který má předem vynásobený Alpha | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-designers
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 05348afa-f079-4f53-a05b-ecd91d13adab
caps.latest.revision: "4"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: f0c8267d1153cf5ea112573e8af5c82ad7e8e805
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-export-a-texture-that-has-premultiplied-alpha"></a>Postupy: Export textury s přednásobeným alfa
Kanál obsahu bitové kopie můžete vygenerovat předem vynásobí alfa textury zdrojové bitové kopie. To může být jednodušší použít a větší odolnost než u textury, které neobsahují předem vynásobí alfa.  
  
 Tento dokument ukazuje tyto aktivity:  
  
-   Konfigurace zdrojové bitové kopie na zpracování kanálu obsahu bitové kopie.  
  
-   Konfigurace obsahu kanálu bitové kopie, který se má generovat předem vynásobí alpha.  
  
## <a name="premultiplied-alpha"></a>Předem vynásobí Alpha  
 Předem vynásobí alpha nabízí několik výhod oproti konvenční, předem vynásobený alfa, protože lépe představuje interakci reálného světla s fyzické materiály oddělením příspěvek texel barvu (barvu, která se přidá do scény) z jeho průsvitnosti (velikost základní barvu, která umožňuje prostřednictvím). Některé z výhod použití předem vynásobí alpha jsou:  
  
-   Prolnutí alfa předem vynásobí je asociativní operace; Výsledek prolnutí více průhledná textury je stejný, bez ohledu na pořadí, ve kterém jsou smíšení textury.  
  
-   Z důvodu asociativní povaha prolnutí alfa předem vynásobí je zjednodušený více průchodu vykreslování průhledné objekty.  
  
-   Pomocí předem vynásobí alpha čistý sčítání prolnutí (podle nastavení alfa nula) i lineárně interpolované prolnutí lze dosáhnout současně. Například v rámci systému částice additively kombinaci ještě efektivněji částice se může stát průhledná kouře částice, který je smíšení pomocí lineární interpolace. Bez předem vynásobí alpha by mít kreslení částice ještě efektivněji samostatně z kouře částice a změnit stav vykreslení mezi kreslení volání.  
  
-   Textury, které používají předem vynásobí alpha komprimovat s vyšší kvality než ty, které nejsou, a jejich nemáte vykazovat zabarvené okrajů – nebo "aureolu vliv" –, může dojít při přizpůsobte textury, které nepoužívají předem vynásobí alfa.  
  
#### <a name="to-create-a-texture-that-uses-premultiplied-alpha"></a>Chcete-li vytvořit texture, který používá předem vynásobí alpha  
  
1.  Začněte základní texturou. Nahrajte existující soubor bitové kopie, nebo ji vytvořte jak je popsáno v [postupy: vytvoření základní Texture](../designers/how-to-create-a-basic-texture.md).  
  
2.  Soubor textury nakonfigurujte, aby se zpracování obsahu kanálu bitové kopie. V **Průzkumníku řešení**, otevřete místní nabídku pro soubor textury a zvolte **vlastnosti**. Na **vlastnosti konfigurace**, **Obecné** nastavte **typ položky** vlastnost **bitové kopie obsahu kanálu**. Ujistěte se, že **obsahu** je nastavena na **Ano** a **vyloučit ze sestavení** je nastaven na **ne**a potom vyberte  **Použít** tlačítko. **Bitové kopie obsahu kanálu** zobrazí se stránka vlastností konfigurace.  
  
3.  Konfiguraci kanálu bitové kopie obsahu k vygenerování předem vynásobí alfa. Na **vlastnosti konfigurace**, **bitové kopie obsahu kanálu**, **Obecné** nastavte **převést na formát předem vynásobená alfa** Vlastnost **Ano (nebo generatepremultipliedalpha)**.  
  
4.  Vyberte **OK** tlačítko.  
  
 Při sestavování projektu bitové kopie obsahu kanálu převede zdrojové bitové kopie z formátu práci na výstupní formát, který jste zadali – to zahrnuje převod bitovou kopii do předem vynásobí alfa formátu – a výsledek je zkopírovat na výstup projektu adresář.