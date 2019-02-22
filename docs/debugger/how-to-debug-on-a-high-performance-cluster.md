---
title: 'Postupy: Ladění na vysoký výkon clusteru | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- cluster debugging
- high-performance debugging
ms.assetid: a2f0eb07-840e-4f95-a1b1-9509217e5b8f
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 8eedc9c469e4ceb4ac4b5be018f2ebdd227ffcf2
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56681787"
---
# <a name="how-to-debug-on-a-high-performance-cluster-c-visual-basic-c"></a>Postupy: Ladění na vysoký výkon clusteru (C#, Visual Basic, C++)

Ladění programu multiprocesingem na vysoký výkon clusteru je jako ladění program ve vzdáleném počítači. Existuje ale několik dalších důležitých informací. Obecné nastavení vzdálené požadavky najdete v tématu [vzdálené ladění](../debugger/remote-debugging.md).

 Při ladění na vysoký výkon clusteru můžete použít všechny [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] ladění systému windows a techniky, které jsou k dispozici pro vzdálené ladění. Vzhledem k tomu, že ladíte vzdáleně, ale okno externí konzoly není k dispozici.

 **Vlákna** okno a **procesy** jsou obzvláště užitečné pro ladění paralelních aplikací. Tipy k používání těchto oken naleznete v tématu [jak: Použití okna procesy](/previous-versions/visualstudio/visual-studio-2010/7h8h5sdw(v=vs.100)) a [názorný postup: Ladění pomocí okna vlákna](../debugger/how-to-use-the-threads-window.md).

 Následující postupy ukazují některé techniky, které jsou obzvláště užitečné pro ladění na vysoký výkon clusteru.

 Při ladění paralelní aplikace můžete nastavit zarážku na konkrétní vlákno, proces nebo počítače. Můžete to provést vytvořením normální zarážky a následným přidáním filtru zarážky.

### <a name="to-open-the-breakpoint-filter-dialog-box"></a>Chcete-li otevřít dialogové okno Filtr zarážek

1.  Klikněte pravým tlačítkem na piktogram zarážky v okně zdroje **zpětný překlad** okně **zásobník volání** okna, nebo **zarážky** okno.

2.  V místní nabídce klikněte na tlačítko **filtr**. Tato možnost může zobrazit v nejvyšší úrovni nebo v podnabídce v části **zarážky**.

### <a name="to-set-a-breakpoint-on-a-specific-computer"></a>Chcete-li nastavit zarážku v určitém počítači

1.  Získejte název počítače z **procesy** okna.

2.  Vyberte zarážku a otevřete **filtr zarážek** dialogovému oknu, jak je popsáno v předchozím postupu.

3.  V **filtr zarážek** dialogové okno, zadejte:

     MachineName =*yourmachinename*

     Chcete-li vytvořit složitější filtr, můžete kombinovat klauzule pomocí `&`, operátoru AND `||`, operátoru OR `!`, operátoru NOT a závorek.

4.  Klikněte na **OK**.

### <a name="to-set-a-breakpoint-on-a-specific-process"></a>Nastavení zarážky v konkrétním procesu

1.  Získejte název procesu nebo ID procesu z **procesy** okna.

2.  Vyberte zarážku a otevřete **filtr zarážek** dialogové okno stejně jako v prvním postupu.

3.  V **filtr zarážek** dialogové okno, zadejte:

     `ProcessName =`  *yourprocessname*

     —nebo—

     `ProcessID =` *yourprocessIDnumber*

     Chcete-li vytvořit složitější filtr, můžete kombinovat klauzule pomocí `&`, operátoru AND `||`, operátoru OR `!`, operátoru NOT a závorek.

4.  Klikněte na **OK**.

### <a name="to-set-a-breakpoint-on-a-specific-thread"></a>Nastavení zarážky v konkrétním vlákně

1.  Získejte název vlákna nebo ID vlákna z **vlákna** okna.

2.  Vyberte zarážku a otevřete **filtr zarážek** dialogovému oknu, jak je popsáno v prvním postupu.

3.  V **filtr zarážek** dialogové okno, zadejte:

     `ThreadName =` *yourthreadname*

     —nebo—

     `ThreadID =` *yourthreadIDnumber*

     Chcete-li vytvořit složitější filtr, můžete kombinovat klauzule pomocí `&`, operátoru AND `||`, operátoru OR `!`, operátoru NOT a závorek.

4.  Klikněte na **OK**.

## <a name="example"></a>Příklad
 Následující příklad ukazuje, jak vytvořit filtr pro zarážku v počítači s názvem `marvin` a vlákno s názvem `fourier1`.

`(MachineName = marvin) & (ThreadName = fourier1)`


## <a name="see-also"></a>Viz také
- [Ladění vícevláknových aplikací](../debugger/debug-multithreaded-applications-in-visual-studio.md)
- [Vzdálené ladění](../debugger/remote-debugging.md)
- [Postupy: Použití okna procesy](/previous-versions/visualstudio/visual-studio-2010/7h8h5sdw(v=vs.100))
- [Začínáme s laděním vícevláknových aplikací](../debugger/get-started-debugging-multithreaded-apps.md)
- [Vláken a procesů](/previous-versions/visualstudio/visual-studio-2010/ms164740(v=vs.100))
- [Použití zarážek](../debugger/using-breakpoints.md)