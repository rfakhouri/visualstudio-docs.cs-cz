---
title: "Postupy: vytvoření a změna úrovně MIP | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-designers
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f64d4369-2307-4175-a39a-2e45506f7fa1
caps.latest.revision: "14"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 18f7aa6c48b0f1deebd292193d46119e8a97c4b6
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-create-and-modify-mip-levels"></a>Postupy: Vytvoření a úprava úrovní MIP
Tento dokument ukazuje, jak používat **Editor obrázků** ke generování a úpravě *MIP úrovně* texture místo úroveň z – podrobnosti (mez stanovitelnosti).  
  
## <a name="generating-mip-levels"></a>Generování MIP úrovně  
 *Mipmapping* je technika, který slouží ke zvýšení rychlosti vykreslování a snížit aliasy artefakty na texturou objekty podle předem výpočet a ukládání několik kopií texturou v různých velikostech. Každá kopie, což se označuje jako MIP úroveň, je poloviční šířky a výšky předchozí kopie. Po vykreslení texturou na povrchu objektu MIP úroveň, která nejvíce odpovídá oblasti místo na obrazovce texturou prostor, je automaticky vybrán. To znamená, že hardware grafiky nemá vyfiltrujete příliš velký textury pro zachování konzistentní visual kvality. O 33 procent více než původní texture samostatně sice paměti náklady na ukládání MIP úrovně výkonu a zvýšení kvality obrázku justify ho.  
  
#### <a name="to-generate-mip-levels"></a>Ke generování MIP úrovně  
  
1.  Začínat základní texture, jak je popsáno v [postupy: vytvoření základní Texture](../designers/how-to-create-a-basic-texture.md). Nejlepších výsledků dosáhnete, zadejte texture, který má šířka a výška, které jsou power dva velikosti, například 256, 512, 1024, a tak dále.  
  
2.  Generovat MIP úrovně. Na **režimu Editor obrázků** nástrojů vyberte **Upřesnit**, **nástroje**, **generovat Mips**.  
  
     Všimněte si, že **přejít na další úroveň Mip** a **přejít na předchozí úrovně Mip** tlačítka se zobrazují na **režimu Editor obrázků** panelu nástrojů. Pokud **vlastnosti** zobrazí se okno, Všimněte si také, že vlastnosti jen pro čtení **Mip úroveň** a **Mip úroveň počet** se nyní zobrazí v vlastnosti bitové kopie.  
  
## <a name="modifying-mip-levels"></a>Úprava MIP úrovně  
 K dosažení speciální efekty nebo zvýšení kvality obrázku konkrétní úrovně podrobností, můžete upravit jednotlivé úrovně MIP jednotlivě. Například můžete udělit objekt texturou jiný vzhled ve vzdálenosti (větší vzdálenosti odpovídá menší MIP úrovně), nebo můžete zajistit, že textury, které obsahují text nebo symboly zůstat čitelné i na menší MIP úrovních.  
  
#### <a name="to-modify-an-individual-mip-level"></a>Chcete-li změnit úroveň jednotlivých MIP  
  
1.  Vyberte úroveň MIP, kterou chcete upravit. Na **režimu Editor obrázků** nástrojů, použijte **přejít na další úroveň MIP** a **přejít na předchozí úrovně MIP** tlačítka pro přesun mezi úrovněmi MIP.  
  
2.  Po výběru MIP úroveň, kterou chcete upravit, můžete to změnit, aniž byste museli měnit obsah jiných úrovních MIP nástrojů pro kreslení. Kreslení nástroje jsou k dispozici na **Editor obrázků** panelu nástrojů. Jakmile vyberete nástroj, můžete změnit jeho vlastnosti v **vlastnosti** okno. Informace o nástrojů pro kreslení a jejich vlastnostech najdete v tématu [Editor obrázků](../designers/image-editor.md).  
  
> [!NOTE]
>  Pokud není potřeba upravovat obsah jednotlivých úrovní MIP – jako mohou k dosažení určité účinky – doporučujeme generování mipmaps z texture zdroje v čase vytvoření buildu. To pomáhá zajistit, že MIP úrovně zůstat synchronizované s texture zdroje, protože úpravy na úrovni MIP nejsou automaticky rozšíří na jiných úrovních. Další informace o tom, jak vygenerovat mipmaps v čase vytvoření buildu najdete v tématu [postupy: Export texturou této obsahuje Mipmaps](../designers/how-to-export-a-texture-that-contains-mipmaps.md).  
  
## <a name="see-also"></a>Viz také  
 [Postupy: vytvoření základní textury](../designers/how-to-create-a-basic-texture.md)