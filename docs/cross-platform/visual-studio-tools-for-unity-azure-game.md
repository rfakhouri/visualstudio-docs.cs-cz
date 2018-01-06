---
title: "Visual Studio Tools for Unity Azure návod herní | Microsoft Docs"
ms.custom: 
ms.date: 10/19/2017
ms.reviewer: crdun
ms.suite: 
ms.technology: tgt-pltfrm-cross-plat
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: DA86FC7F-E456-4DFC-84BF-D780421508B9
author: dantogno
ms.author: v-davian
manager: crdun
ms.workload:
- azure
- unity
ms.openlocfilehash: 7d0a7da4093b8f90ab76dee55f1ec9ad6dc21679
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="test-the-sample-game"></a>Test Ukázka hry

Herní ukázka je jednoduché dostihy hra, který zaznamenává data o chování zobrazujícím a ukládá je snadno tabulky Azure. Ukázka herní také zahrnuje scény, které číst data z Azure a vizualizovat pro přehrávač.

V této části se jednoduše vysvětlují, jak ve hře ukázka a ujistěte se, že je správně funguje. V dalších oddílech přejde do více podrobností, která vysvětluje, jak funguje herní ukázka.

## <a name="starting-the-game"></a>Zahájení hry

1. V okně Unity projektu, přejděte na **prostředky nebo Azure snadno tabulky ukázkové herní prostředky nebo scény** složky.

2. Klikněte dvakrát **MenuScene** ho otevřete.

3. V okně hra Unity klikněte na **poměr stran rozevírací** a zvolte **16:9**.

  ![Poměr stran sady](media/vstu_azure-test-sample-game-image1.png)

4. Klikněte **přehrání** tlačítko spustit hru v editoru Unity.


## <a name="complete-a-race"></a>Dokončení závodu

Před zobrazením žebříček nebo heatmap, je nejlepší vytvořit ukázková data pomocí soupeření alespoň jednou.

1. Herní spuštěna v editoru Unity, klikněte na **soupeření!** tlačítko spustit novou soupeření.

2. Použití **WASD** nebo **klávesy se šipkami** jednotka Auto a dokončete po směru hodinových ručiček okruhu kolem sledování. Z důvodu příklad nezapomeňte do některé bariéry na cestě k chybě. Ladění výstupu v Unity konzoly by měl signalizují, že kolize byl zaznamenán.

  >[!NOTE]
  > Pokud budete spravovat k převrácení Auto a nelze pokračovat, klikněte na tlačítko **restartujte**. Data je odeslán, pouze do Azure po dokončení okruhu.

  ![Spustit závodu](media/vstu_azure-test-sample-game-image2.png)

3. Po překročení meze šachovnicová mřížka řádku dokončit, by se měla zobrazovat ve hře **dokončeno** zprávy. V tomto okamžiku data o chybách budou odeslány do Azure.

4. Pokud jste dokončili jednoho okruhu nejrychlejší prvních 10 dobu, zobrazí se výzva k zadání názvu vysoké skóre. Zadejte název a klikněte na **odeslání**.

  ![Spustit závodu](media/vstu_azure-test-sample-game-image3.png)

## <a name="view-the-heatmap"></a>Zobrazení heatmap

1. Klikněte na tlačítko **zobrazení havárií Heatmap** tlačítko z scény soupeření nebo vyberte **havárií Heatmap** z hlavní nabídky.

2. Scény heatmap načte data z tabulky CrashInfo v Azure a zobrazí transparentní red oblasti v umístěních, kde mají nebyly přehrávače v souladu s bariéry dráhy soupeření. Dojde-li více dojde k chybě v překrývající se oblasti, by se zobrazit oblasti své světlejší.

  ![Heatmap](media/vstu_azure-test-sample-game-image4.png)

## <a name="view-the-leaderboard"></a>Zobrazení žebříček

1. Klikněte **žebříček** tlačítko z soupeření scény nebo hlavní nabídky.

2. Scény žebříček načte vysoké skóre data z tabulky HighScoreInfo v Azure a zobrazí čas player název a okruhu pro každý vysokou stanovení skóre položku.

  ![Žebříček](media/vstu_azure-test-sample-game-image5.png)

## <a name="next-step"></a>Další krok

* [Vysvětlení k RaceScene](visual-studio-tools-for-unity-azure-racescene.md)
