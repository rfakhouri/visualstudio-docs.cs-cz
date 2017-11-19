---
title: "Postupy: přidání aktivit do sady nástrojů | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: b3a8a785-5928-457a-8a50-30267e29503d
caps.latest.revision: "16"
author: ErikRe
ms.author: erikre
manager: erikre
ms.openlocfilehash: 23e042a7ff34163872b3a932b105bc3b452023ee
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="how-to-add-activities-to-the-toolbox"></a>Postupy: přidání aktivit do sady nástrojů
Aktivity mohou být přidány do **sada nástrojů** ve vašem řešení v několika různými způsoby. Můžete přidat z aktuálního projektu, na ně odkazovat z jiného projektu nebo na ně odkazovat z jiného sestavení.  
  
### <a name="to-add-an-activity-from-within-your-current-project"></a>Chcete-li přidat aktivitu z v aktuálním projektu  
  
1.  Přidejte novou vlastní aktivitu do aktuálního projektu pracovního postupu. [!INCLUDE[crabout](../test/includes/crabout_md.md)]Přidání nové vlastní aktivity do projektu, najdete v části [postupy: Přidat novou položku do projektu Workflow](../workflow-designer/how-to-add-a-new-item-to-a-workflow-project.md).  
  
2.  Přidáte vlastní logiky do vaši aktivitu.  
  
3.  Sestavte projekt. Pokud bylo úspěšné, sestavení novou kategorii v **sada nástrojů** s názvem "\<*název projektu*>" se zobrazí s vlastní aktivity, které jsou součástí této kategorie spadají.  
  
    > [!NOTE]
    >  Pokud se resetuje sady nástrojů, vlastní aktivity se odebere, i v případě, že je řešení znovu sestaven. Znovu naplnit nástrojů vlastní aktivity po byla obnovena, restartujte [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)].  
  
    > [!NOTE]
    >  V panelu nástrojů můžete zobrazit pouze jednu aktivitu daného názvu. Pokud dvě aktivity z různých sestavení mají stejný název třídy, se zobrazí pouze jeden.  
  
    > [!NOTE]
    >  Doména aplikace je sdílen mezi editor instance; Pokud se používají statické proměnné, bude sdílena mezi také instance editoru. Pokud není toto chování žádoucí, služby slouží ke sledování proměnné instancí. V tématu [pomocí kontextu úpravy typem ModelItem](/dotnet/framework/windows-workflow-foundation/using-the-modelitem-editing-context) informace o používání služby v návrháři.  
  
### <a name="to-add-an-activity-from-within-a-different-project"></a>Chcete-li přidat aktivitu z v rámci jiného projektu  
  
1.  Otevřete řešení, které obsahuje alespoň jeden pracovní postup projekt a projekt knihovny vlastní aktivity nebo jiného projektu pracovního postupu, který definuje vlastní aktivity.  
  
2.  Sestavení obou projektů. Pokud sestavení, které byly úspěšné, novou kategorii v **sada nástrojů** s názvem "\<*název projektu*>" se zobrazí s vlastní aktivity, které jsou součástí této kategorie spadají.  
  
### <a name="to-add-an-activity-to-the-toolbox-from-an-assembly"></a>Chcete-li přidat aktivity do sady nástrojů ze sestavení  
  
1.  Otevřete řešení pracovního postupu.  
  
2.  Z **nástroje** nabídce vyberte možnost **výběr položek sady nástrojů...** .  
  
3.  V **výběr položek sady nástrojů** dialogové okno, vyberte **systém. součásti** kartě a pak klikněte na **Procházet...**  přejděte na sestavení, které obsahuje vlastní aktivity chcete přidat.  
  
4.  Vyberte sestavení a klikněte na **OK**. Součást vlastní aktivity se přidá do seznamu součástí a je automaticky vybrán.  
  
    1.  Klikněte na tlačítko **OK** zavřete dialogové okno.  
  
5.  Pokud chcete zobrazit sady nástrojů, vyberte **sada nástrojů** z **zobrazení** nabídky.  
  
6.  Vlastní aktivity se zobrazí v **sada nástrojů** v kategorii, která byla aktivní před přidáním položky. Například pokud **Obecné** kategorie byla vybrána v **sada nástrojů** před přidáním položky panelu nástrojů, tato aktivita se zobrazí v části **Obecné** kategorie.  
  
## <a name="see-also"></a>Viz také  
 [Pomocí návrháře pracovních postupů](../workflow-designer/using-the-workflow-designer.md)