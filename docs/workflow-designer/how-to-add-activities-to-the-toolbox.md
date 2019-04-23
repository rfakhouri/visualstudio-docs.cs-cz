---
title: 'Návrhář postupu provádění – jak: Přidání aktivit do panelu nástrojů'
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: b3a8a785-5928-457a-8a50-30267e29503d
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: b9e50736e5d9bc55eadf0aab7e7f00d26eb03249
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60117236"
---
# <a name="how-to-add-activities-to-the-toolbox"></a>Postupy: Přidání aktivit do panelu nástrojů

Aktivity mohou být přidány do **nástrojů** ve vašem řešení v několika různými způsoby. Můžete přidat z v rámci aktuálního projektu, odkazovat z jiného projektu nebo na ně odkazovat z jiného sestavení.

## <a name="to-add-an-activity-from-within-your-current-project"></a>Chcete-li přidat aktivitu z v rámci aktuálního projektu

1. Přidáte novou vlastní aktivitu do aktuálního projektu pracovního postupu. Další informace o přidání do projektu novou vlastní aktivitu, naleznete v tématu [jak: Přidat novou položku do projektu pracovního postupu](../workflow-designer/how-to-add-a-new-item-to-a-workflow-project.md).

2. Přidáte vlastní logiku aktivity.

3. Sestavte projekt. Pokud bylo sestavení úspěšné, novou kategorii v **nástrojů** s názvem "\<*název projektu*>" se zobrazí s vlastní aktivity zahrnuté do této kategorie spadají.

    > [!NOTE]
    > Pokud panel nástrojů se vynuluje, vlastní aktivity se odebere, i v případě, řešení je vybudováno znovu. Naplnit panel nástrojů s vlastní aktivity po byla obnovena, restartujte Visual Studio.

    > [!NOTE]
    > Panel nástrojů můžete zobrazit pouze jednu aktivitu daným názvem. Pokud dvě aktivity v různých sestaveních mají stejný název třídy, zobrazí se jenom jeden.

    > [!NOTE]
    > Domény aplikace se sdílí mezi instance editoru; Pokud používáte statické proměnné, bude sdílena mezi instance editoru i. Pokud to není požadované chování, služba by měla sloužit ke sledování proměnné instance. Zobrazit [použití kontextu úprav ModelItem](/dotnet/framework/windows-workflow-foundation/using-the-modelitem-editing-context) informace o používání služby v rámci návrháře.

## <a name="to-add-an-activity-from-within-a-different-project"></a>Chcete-li přidat aktivitu z v rámci jiného projektu

1. Otevřete řešení, která obsahuje alespoň jeden projekt pracovního postupu a projektu knihovny vlastní aktivity nebo jiný projekt pracovního postupu, který definuje vlastní aktivity.

2. Vytvářejte obou projektů. Je-li sestavení úspěšné, novou kategorii v **nástrojů** s názvem "\<*název projektu*>" se zobrazí s vlastní aktivity zahrnuté do této kategorie spadají.

## <a name="to-add-an-activity-to-the-toolbox-from-an-assembly"></a>Chcete-li přidat aktivitu do panelu nástrojů ze sestavení

1. Otevřete řešení pracovního postupu.

2. Z **nástroje** nabídce vyberte možnost **zvolit položky nástrojů**.

3. V **zvolit položky nástrojů** dialogové okno, vyberte **komponenty System.Activities** kartu a potom klikněte na **Procházet** přejít na sestavení, který obsahuje vlastní aktivity, které chcete přidat.

4. Vyberte sestavení a klikněte na tlačítko **OK**. Komponentu vlastní aktivity se přidá do seznamu součástí a se vybere automaticky.

    1. Klikněte na tlačítko **OK** zavřete dialogové okno.

5. Chcete-li zobrazit panel nástrojů, vyberte **nástrojů** z **zobrazení** nabídky.

6. Vlastní aktivity se zobrazí v **nástrojů** v kategorii, která byla aktivní před byla položka přidána. Například pokud **Obecné** kategorie vybraného v **nástrojů** před přidáním položku sady nástrojů, tato aktivita se zobrazí v části **Obecné** kategorie.

## <a name="see-also"></a>Viz také:

- [Používání návrháře postupu provádění](developing-applications-with-the-workflow-designer.md)