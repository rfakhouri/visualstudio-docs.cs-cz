---
title: "Visual Studio Tools for Unity Azure návod instalace | Microsoft Docs"
ms.custom: 
ms.date: 10/19/2017
ms.reviewer: crdun
ms.suite: 
ms.technology: tgt-pltfrm-cross-plat
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: FFE17FC6-0B47-4A00-A125-01BD49E3873C
author: dantogno
ms.author: v-davian
manager: crdun
ms.workload:
- azure
- unity
ms.openlocfilehash: ba9de2e6af5c066e83b75576f9b104f20908aec6
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="create-easy-tables"></a>Vytváření snadno tabulek

Nyní když máte mobilní aplikace v Azure s snadno tabulky inicializován, je čas vytvořit tabulky, které bude udržovat přehled o dat odesílaných ze hra Unity.

## <a name="setup-the-crash-heatmap-table"></a>Instalační program v tabulce heatmap havárií

1. Na portálu Azure klikněte na možnost všechny prostředky a potom vyberte mobilní aplikace, který jste nakonfigurovali pro snadné tabulky v předchozích krocích.

  ![Vyberte mobilní aplikace](media/vstu_azure-setup-table-schema-image1.png)

2. Přejděte dolů k položce **MOBILE** nadpis a vyberte **snadno tabulky**. Už musí být všechny oznámení o inicializaci aplikace pro snadné tabulky.  

  ![Vyberte snadno tabulky](media/vstu_azure-setup-table-schema-image2.png)

3. Klikněte **přidat** tlačítko.

  ![Klikněte na tlačítko Přidat](media/vstu_azure-setup-table-schema-image3.png)

4. Název tabulky "**CrashInfo**" a klikněte na tlačítko **OK**. Ponechejte zbývající možnosti ve výchozím nastavení.

  > [!WARNING]
  > Tento název musí odpovídat názvu třídy datového modelu, vytvořit později v tomto návodu.

  ![Název a klikněte na tlačítko OK](media/vstu_azure-setup-table-schema-image4.png)

5. Přečte oznámení po vytvoření nové tabulky.

> [!NOTE]
> S snadno tabulky je schéma tabulky ve skutečnosti dynamicky vytvořen jako přibývají data. To znamená, že příslušná data sloupce není nutné ručně nastavit v tomto kroku.

## <a name="setup-the-leaderboard-table"></a>Instalační program v tabulce žebříček

1. Přejděte zpět do okna snadno tabulky a klikněte na tlačítko **přidat** přidat v druhé tabulce.

  ![Přidat v druhé tabulce](media/vstu_azure-setup-table-schema-image10.png)

2. Pojmenujte novou tabulku "**HighScoreInfo**" a klikněte na tlačítko **OK**. Ponechejte zbývající možnosti na jejich výchozí nastavení.

  > [!WARNING]
  > Tento název musí odpovídat názvu třídy datového modelu, vytvořit později v tomto návodu.

  ![Název a klikněte na tlačítko OK](media/vstu_azure-setup-table-schema-image11.png)

3. Přečte oznámení po vytvoření nové tabulky.


## <a name="next-step"></a>Další krok

* [Příprava vývojového prostředí](visual-studio-tools-for-unity-azure-prepare.md)
