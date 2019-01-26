---
title: Výběr položek sady nástrojů, součásti WPF
ms.date: 06/21/2017
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- vs.chooseitems.wpfcomponents
helpviewer_keywords:
- WPF Components tab, Choose Toolbox Items dialog box
- Choose Toolbox Items dialog box, WPF Components tab
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 98000fda073cf480ad7204912ffa1461c4bdc5ae
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55008761"
---
# <a name="choose-toolbox-items-wpf-components"></a>Zvolit položky panelu nástrojů, součásti WPF

Tato karta **zvolit položky nástrojů** dialogové okno zobrazí seznam dostupných ovládacích prvků Windows Presentation Foundation (WPF) v místním počítači. Chcete-li zobrazit tento seznam, vyberte **zvolit položky nástrojů** z **nástroje** nabídku zobrazíte **zvolit položky nástrojů** dialogové okno a pak vyberte jeho **WPF Součásti** kartu. Součástí uvedené seřadit, vyberte libovolné záhlaví sloupce.

- Pokud je zaškrtnuto políčko vedle komponenty, bude zobrazena ikona pro danou součást v **nástrojů**.

    > [!TIP]
    > Chcete-li přidat ovládací prvek WPF dokumentu projektu, který je otevřen pro úpravy, přetáhněte jeho **nástrojů** ikonu na návrhovou plochu zobrazení. Výchozí značky a pro součásti jsou vloženy do svého projektu můžete upravit. Další informace najdete v tématu [nástrojů](../../ide/reference/toolbox.md).

- Pokud je zrušeno zaškrtnutí políčka vedle komponenty, příslušnou ikonu se odebere z **nástrojů**.

    > [!NOTE]
    > Součásti rozhraní .NET Framework nainstalované v počítači nadále k dispozici, zda jsou ikony pro ně zobrazí **nástrojů**.

Sloupce **součásti WPF** karta obsahovat následující informace:

**Název**

Seznamy názvů ovládacích prvků WPF pro položky, které existují v registru počítače.

**Namespace**

Zobrazuje hierarchii [rozhraní .NET Framework třída API](/dotnet/api/?view=netframework-4.7) obor názvů, který definuje strukturu komponenty. Výsledky můžete řadit podle sloupce seznam součástí, které jsou v každém oboru názvů rozhraní .NET Framework nainstalované v počítači k dispozici.

**Název sestavení**

Zobrazí název sestavení rozhraní .NET Framework, který obsahuje obor názvů pro jednotlivé komponenty. Výsledky můžete řadit podle sloupce do seznamu oborů názvů obsažené v každé sestavení rozhraní .NET Framework nainstalované v počítači.

**Adresář**

Zobrazí umístění sestavení rozhraní .NET Framework. Je výchozím umístěním pro všechna sestavení do globální mezipaměti sestavení. Další informace o globální mezipaměti sestavení, naleznete v tématu [práce se sestaveními a s globální pamětí sestavení](/dotnet/framework/app-domains/working-with-assemblies-and-the-gac).

## <a name="uielement-list"></a>Seznam prvků uživatelského rozhraní

### <a name="filter"></a>Filtr

Filtruje seznam ovládacích prvků WPF na základě řetězce, které zadáte do textového pole. Jsou uvedeny všechny shody z kteréhokoli čtyři sloupce.

**Vymazat**

Vymaže řetězec filtru.

**Procházet**

Otevře **otevřít** dialogové okno, které vám umožní přejít do sestavení, které obsahují ovládací prvky WPF. Použijte k načtení sestavení, které nejsou umístěné v globální mezipaměti sestavení.

**Jazyk**

Ukazuje lokalizovaného jazyka sestavení, který obsahuje vybraný ovládací prvek WPF.

## <a name="limitations"></a>Omezení

Přidání vlastního ovládacího prvku nebo <xref:System.Windows.Controls.UserControl> do panelu nástrojů má následující omezení:

- Platí jenom pro vlastní ovládací prvky, které jsou definovány mimo aktuální projekt.

- Nelze aktualizovat správně při změně konfigurace řešení v ladicí verzi nebo z verze pro ladění. Je to proto, že odkaz není odkaz na projekt, ale místo toho je pro sestavení na disku. Pokud je ovládací prvek součástí aktuálního řešení, když změníte z ladicí verze, váš projekt i nadále odkazují na ladicí verze ovládacího prvku.

Kromě toho pokud metadat v době návrhu platí pro vlastní ovládací prvek a tato metadata Určuje, že <xref:Microsoft.Windows.Design.ToolboxBrowsableAttribute> je nastavena na `false`, ovládací prvek se nezobrazí v panelu nástrojů.

Ovládací prvky přímo v XAML zobrazení můžete odkazovat pomocí mapování oboru názvů a sestavení pro ovládací prvek.

## <a name="see-also"></a>Viz také:

- [Panel nástrojů](../../ide/reference/toolbox.md)
- [Začínáme s WPF](../../designers/getting-started-with-wpf.md)
