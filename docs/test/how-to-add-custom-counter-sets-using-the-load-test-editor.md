---
title: "Přidání vlastních sad čítačů pro zatížení testování v sadě Visual Studio | Microsoft Docs"
ms.date: 10/19/2016
ms.topic: article
helpviewer_keywords:
- counters, counter sets
- counter sets
- load tests, counter sets
ms.assetid: 499aca80-1069-408d-ac68-326da6a50645
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-ide-test
ms.openlocfilehash: 8f691c0eac38dae9e9f419335eb1d3ae87c693df
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/19/2018
---
# <a name="how-to-add-custom-counter-sets-using-the-load-test-editor"></a>Postupy: Přidání vlastních sad čítačů pomocí editoru zátěžových testů

Když vytvoříte zátěžový test pomocí **načíst testování Průvodce novým**, přidáte počáteční sadu čítačů. Ty nabízejí sadu předdefinovaných sad čítačů pro zátěžové testy.

> [!NOTE]
> Pokud jsou zátěžové testy distribuovány napříč vzdálenými počítači, jsou čítače kontroléru a agentů namapovány na sady čítačů kontrolérů a agentů. Další informace o použití vzdáleného počítače v zátěžovém testu najdete v tématu [testovací kontrolery a testovací agenti](configure-test-agents-and-controllers-for-load-tests.md).

Spravovat vaše čítače v **editoru zátěžových testů**. Sady čítačů, které již byly přidány k testovací jsou viditelné v **nastaví čítač** pracovního zátěžového testu. Po vytvoření zátěžového testu k němu lze přidat nové vlastní sady čítačů.

![Custom Counter Set](../test/media/loadtestcustomcounter.png "LoadTestCustomCounter")

## <a name="to-add-a-custom-counter-set-to-a-load-test"></a>Přidání vlastní sady čítačů k zátěžovému testu

1.  Otevřete zátěžový test.

2.  Rozbalte **sad čítačů** uzlu. Jsou zobrazeny všechny sady čítačů, které byly přidány do zátěžového testu.

3.  Klikněte pravým tlačítkem myši **sad čítačů** uzel a vyberte možnost **přidat sadu čítačů vlastní**.

    > [!NOTE]
    > Sada čítačů je zadána výchozí název, například **vlastní1**. Název můžete změnit pomocí **vlastnosti** okno. Zobrazte stisknutím klávesy F4 **vlastnosti** okno.

4.  Chcete-li přidat čítače, které se vaše vlastní čítač nastavit, klikněte pravým tlačítkem na nová množina čítačů a potom zvolte **přidat čítače**. Další informace o tom, jak přidat čítače najdete v tématu [postupy: přidání čítačů do sad čítačů](../test/how-to-add-counters-to-counter-sets-using-the-load-test-editor.md).

    > [!NOTE]
    > Vlastní sadu čítačů lze také přidat kliknutím pravým tlačítkem myši na existující sadu čítačů, výběrem příkazu kopírování a následným vložením do uzlu sad čítačů. Další čítače, které jsou zkopírovány, ale nejsou vyžadovány, je možné odstranit. Můžete změnit název nové sady pomocí čítačů **vlastnosti** okno.

## <a name="see-also"></a>Viz také

- [Určení sad čítačů a mezních pravidel pro počítače v zátěžovém testu](../test/specify-counter-sets-and-threshold-rules-for-load-testing.md)
- [Konfigurace běhu zátěžových testů](../test/configure-load-test-run-settings.md)