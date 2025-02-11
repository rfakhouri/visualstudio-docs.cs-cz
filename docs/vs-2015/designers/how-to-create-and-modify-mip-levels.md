---
title: 'Postupy: Vytvoření a úprava úrovní MIP | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-designers
ms.topic: conceptual
ms.assetid: f64d4369-2307-4175-a39a-2e45506f7fa1
caps.latest.revision: 16
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 1c1d0babfec4a2fd56e2ed40c5f2c75329ccb6d3
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63434462"
---
# <a name="how-to-create-and-modify-mip-levels"></a>Postupy: Vytvoření a úprava úrovní MIP
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Tento dokument popisuje způsob použití **Editor obrázků** k tvorbě a úpravám *úrovní MIP* pro textury místa úrovně of-Detail (lod Level).  
  
## <a name="generating-mip-levels"></a>Generování úrovní MIP  
 *Mipmapping* je technika, která umožňuje zvýšit rychlost vykreslování a snížit třepící artefakty texturovaných objektů a ukládání několik kopií textury v různých velikostech. Každá kopie, která se nazývá úroveň MIP, je poloviční šířku a výšku předchozí kopie. Po vykreslení textury na povrchu objektu je automaticky vybrána úroveň MIP, která nejlépe odpovídá do oblasti místo na obrazovce textury povrchu. To znamená, že grafický hardware nemusí filtrovat textury nadměrné velikosti za k zachování konzistentní vizuální kvality. Přestože paměťové náklady na uložení úrovní MIP je přibližně o 33 procent větší než největší původní textura samostatně, výkon a kvalita obrazu zarovnat ho.  
  
#### <a name="to-generate-mip-levels"></a>Generování úrovní MIP  
  
1. Začněte základní texturou, jak je popsáno v [jak: Vytvoření základní textury](../designers/how-to-create-a-basic-texture.md). Pro dosažení nejlepších výsledků určete texturu, která má šířku a výšku, které jsou násobky 2, například 256, 512, 1024, a tak dále.  
  
2. Generování úrovní MIP. Na **režim editoru obrázků** nástrojů, zvolte **Upřesnit**, **nástroje**, **generovat Mips**.  
  
     Všimněte si, že **přejít na další úroveň Mip** a **přejít na předchozí úroveň Mip** tlačítek se zobrazí na **režim editoru obrázků** nástrojů. Pokud **vlastnosti** se zobrazí okno, Všimněte si také, že vlastnosti jen pro čtení **úroveň Mip** a **počet úrovní Mip** teď budou zobrazovat v dialogovém okně Vlastnosti obrázku.  
  
## <a name="modifying-mip-levels"></a>Změna úrovní MIP  
 Dosáhli zvláštních efektů nebo zvýšili kvalitu obrazu na určité úrovni podrobností, můžete upravit jednotlivé úrovně MIP samostatně. Například texturovaným objektem můžete přidělit jiný vzhled ve vzdálenosti (větší vzdálenost odpovídá NIŽŠÍM úrovním MIP) nebo můžete zajistit, že textury, které obsahují text nebo symboly, zůstanou čitelné i na menší MIP úrovních.  
  
#### <a name="to-modify-an-individual-mip-level"></a>Úprava jednotlivých úrovní MIP  
  
1. Vyberte úroveň MIP, kterou chcete upravit. Na **režim editoru obrázků** nástrojů, použijte **přejít na další úroveň MIP** a **přejít na předchozí úroveň MIP** tlačítka mezi úrovněmi MIP pohybovat.  
  
2. Po výběru úrovně MIP, kterou chcete upravit, můžete použít nástroje pro kreslení k její změně bez změny obsahu jiných úrovních MIP. Kreslicí nástroje jsou k dispozici na **Editor obrázků** nástrojů. Po vybrání nástroje můžete změnit jeho vlastnosti v **vlastnosti** okna. Informace o nástroje pro kreslení a jejich vlastnostech naleznete v tématu [Editor obrázků](../designers/image-editor.md).  
  
> [!NOTE]
> Pokud není potřeba upravovat obsah jednotlivých úrovní MIP, což lze provést k dosažení určitých efektů, doporučujeme generovat mipmapy ze zdrojových textur v okamžiku sestavení. To pomáhá zajistit, že úrovně MIP zůstanou synchronizovány se zdrojovou texturou vzhledem k tomu, že změny na úrovni MIP nejsou automaticky propagovány na další úrovně. Další informace o způsobu generování Mipmap v okamžiku sestavení naleznete v tématu [jak: Export textury obsahující mipmapy](../designers/how-to-export-a-texture-that-contains-mipmaps.md).  
  
## <a name="see-also"></a>Viz také  
 [Postupy: Vytvoření základní textury](../designers/how-to-create-a-basic-texture.md)
