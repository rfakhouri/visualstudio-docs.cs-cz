---
title: 'Postupy: Omezení instrumentace na konkrétní knihovny DLL | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- performance tools, runtime profiling control window
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: b39689219b113343162aa0e814cfa68e2422f08d
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62980912"
---
# <a name="how-to-limit-instrumentation-to-specific-dlls"></a>Postupy: Omezení instrumentace na konkrétní knihovny DLL

Pomocí metody profilace instrumentace můžete omezit shromažďování dat profilování na jeden nebo více knihovny DLL v aplikaci. Chcete-li Profilovat jeden nebo více knihoven DLL v aplikaci, vytvoříte relace výkonu, která zahrnuje. *dll* soubory jako cíle. Můžete určit knihovny DLL, které chcete do profilu jako projekty v řešení sady Visual Studio nebo jako nezávislé binární soubory.

## <a name="to-limit-instrumentation-to-specific-dlls-in-a-visual-studio-solution"></a>K omezení instrumentace na konkrétní knihovny DLL v řešení sady Visual Studio

1. Otevřete řešení, které obsahuje knihovnu DLL v sadě Visual Studio.

2. Na **analyzovat** nabídce vyberte možnost **spustit Průvodce výkonem**.

3. Zvolte **instrumentace** jako metodu profilace a pak klikněte na tlačítko **Další**.

4. Z **které z následujících dostupných cílů chcete profil?**, vyberte název. *Knihovna DLL* projektu a pak klikněte na tlačítko **Další**.

5. Klikněte na tlačítko **Dokončit** ukončíte průvodce a zobrazí novou relaci výkonu v **prohlížeč výkonu** okna.

6. Klikněte pravým tlačítkem na **cíle** a pak vyberte **přidat cílový projekt**.

7. Z **přidat cílový projekt** vyberte spustitelný projekt, který chcete použít k knihovny DLL.

     Volitelné. Můžete přidat všechny projekty knihovny DLL, které chcete do profilu.

8. Zabránění shromažďování dat pro přidání projektu, klikněte pravým tlačítkem na název projektu a poté zrušte zaškrtnutí **instrumentace** zaškrtávací políčko.

## <a name="to-specify-specific-dlls-to-profile-as-independent-binaries"></a>Chcete-li určit konkrétní knihovny DLL do profilu jako nezávislé binárních souborů

1. Otevřít Visual Studio.

2. Na **analyzovat** nabídce vyberte možnost **spustit Průvodce výkonem**.

3. Z **které z následujících dostupných cílů chcete profil**, vyberte **Profilovat dynamickou knihovnu (. Knihovny DLL)** a potom klikněte na tlačítko **Další**.

4. Na druhé stránce průvodce proveďte následující kroky:

    - Zadejte název a cesta k souboru. *dll* soubor, který chcete profil v **cesta ke knihovně Dll**. Můžete také kliknout na tlačítko se třemi tečkami (...) a vyhledejte soubor v **dynamické knihovny DLL do profilu** dialogové okno. Všimněte si, že je nutné zadat kopii. *dll* soubor, který se spustí spustitelný soubor (. *soubor exe*) soubor, který vyberete dále.

    - Zadejte cestu a název spustitelného souboru (. *soubor exe*) soubor, který se budou uplatňovat. *dll* v **cesta ke spustitelnému souboru**. Můžete také kliknout na tlačítko se třemi tečkami (...) a vyhledejte soubor v **spustitelný soubor ke spuštění** dialogové okno.

    - Volitelné. Zadejte jakékoli argumenty příkazového řádku, které chcete předat do spustitelného souboru v **argumenty příkazového řádku**. V případě potřeby zadejte pracovní adresář pro aplikaci v **pracovní adresář**.

    - Klikněte na **Další**.

5. Zvolte **instrumentace** jako metodu profilace a pak klikněte na tlačítko **Další**.

6. Klikněte na tlačítko **Dokončit** ukončíte průvodce a zobrazí novou relaci výkonu v **prohlížeč výkonu** okna.

7. Volitelné. Abyste mohli přidat další. *dll* soubory, klikněte pravým tlačítkem na **cíle** a pak vyberte **přidat cílový binární**. Vyberte soubory z **přidat cílový binární** dialogové okno.

    > [!NOTE]
    > Nezadávejte spustitelný soubor (. *soubor exe*) soubor, který zpracovává knihovny DLL.

## <a name="see-also"></a>Viz také:

[Sběr dat řídit](../profiling/controlling-data-collection.md)
[jak: Omezení instrumentace na konkrétní funkce](../profiling/how-to-limit-instrumentation-to-specific-functions.md)