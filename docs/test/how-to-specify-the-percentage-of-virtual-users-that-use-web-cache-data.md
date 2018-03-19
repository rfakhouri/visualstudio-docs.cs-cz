---
title: "Určení procento z virtuálních uživatelů, která Data ve webové mezipaměti použijte pro zatížení testů v sadě Visual Studio | Microsoft Docs"
ms.date: 10/19/2016
ms.topic: article
helpviewer_keywords:
- load tests, virtual users
ms.assetid: f66d5d43-4121-4487-b27f-d0a0baaf7601
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-ide-test
ms.openlocfilehash: c1aa64c0ecee9f214d1bd892c62ba79090d2ce15
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/19/2018
---
# <a name="how-to-specify-the-percentage-of-virtual-users-that-use-web-cache-data"></a>Postupy: Určení procenta virtuálních uživatelů, kteří používají data ve webové mezipaměti

Po vytvoření vaší zátěžový test pomocí **načíst testování Průvodce novým**, můžete změnit vlastnosti scénáře pro splnění vašich potřeb testování a cíle pomocí **načíst Editor testů**. Úplný seznam vlastnosti scénáře zátěžového testu a jejich popisy najdete v tématu [načíst vlastnosti scénář otestovat](../test/load-test-scenario-properties.md).

**Procento nových uživatelů** je nastavena v okně Vlastnosti. Můžete upravit vlastnosti scénáře zátěžového testu v editoru načíst otestovat.

**Procento nových uživatelů** vlastnost má vliv na způsob ve kterém simuluje zátěžový test, ukládání do mezipaměti, které se provádí pomocí webového prohlížeče. Ve výchozím nastavení **procento nových uživatelů** je nastavena na 0 %. Pokud hodnota **procento nových uživatelů** je nastavena na 100 %, každého testu výkonnosti webu, spusťte v zátěžovém testu je zpracován jako první čas uživatele na web, který nemá žádný obsah z webu v jejich mezipaměti prohlížeče z previ navštíví organizační jednotky. Všechny požadavky v testu webu, včetně všechny závislé požadavky, například bitové kopie, proto se stáhnou.

> [!NOTE]
> Vyžádání stejného zdroje lze uložit do mezipaměti je více než jednou v testu webu, se nestáhnou žádosti.

Pokud jste zatížení testování webu, který má velký počet návratový uživatelů, kteří mohou mít obrázky a další obsah Uložitelný do mezipaměti místně, pak nastavení 100 % pro **procento nových uživatelů** vlastnost vygeneruje informace požadavky na stažení než by tomu bylo v reálného využití. V takovém případě by měl odhadnout procento návštěv na webové stránky, které jsou z první uživatelé webu a nastavte **procento nových uživatelů** vlastnost odpovídajícím způsobem.

## <a name="to-specify-the-agents-to-use-for-a-scenario"></a>Chcete-li určit agenty používat pro scénáře

1.  Otevřete zátěžový test.

     **Editoru zátěžových testů** se zobrazí. Zobrazí se strom zátěžového testu.

2.  V zatížení testovat stromy **scénáře** složky, vyberte uzel scénáři chcete určit agentů pro.

3.  Na **zobrazení** nabídce vyberte možnost **vlastnosti – okno**.

     Tento scénář kategorií a vlastností se zobrazí v okně Vlastnosti.

4.  Nastavit hodnotu pro **procento nových uživatelů** vlastnost tak, že zadáte číslo pro procento nových uživatelů.

5.  Po dokončení změn vlastnosti, vyberte **Uložit** na **souboru** nabídky. Potom můžete spustit vaší zátěžového testu pomocí nové **procento nových uživatelů** hodnotu.

## <a name="see-also"></a>Viz také

- [Úpravy scénářů zátěžových testů](../test/edit-load-test-scenarios.md)
- [Návod: Vytvoření a spuštění zátěžového testu](../test/walkthrough-create-and-run-a-load-test.md)
- [Testovací kontrolery a testovací agenti](configure-test-agents-and-controllers-for-load-tests.md)
- [Vlastnosti scénáře zátěžového testu](../test/load-test-scenario-properties.md)
- [Úpravy vzorů zatížení pro modelování aktivit virtuálních uživatelů](../test/edit-load-patterns-to-model-virtual-user-activities.md)