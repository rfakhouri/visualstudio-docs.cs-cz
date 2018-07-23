---
title: 'Postupy: reakce na ladicí program Just-In-Time | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 05/23/17
ms.technology: vs-ide-debug
ms.topic: troubleshooting
helpviewer_keywords:
- debugging [Visual Studio], Just-In-Time
- Just-In-Time debugging
ms.assetid: 14972d5f-69bc-479b-9529-03b8787b118f
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: fd3f565d8bb58ae290b0b569bb61d4cb57e8edaa
ms.sourcegitcommit: 5b767247b3d819a99deb0dbce729a0562b9654ba
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/20/2018
ms.locfileid: "39179772"
---
# <a name="how-to-respond-to-the-just-in-time-debugger"></a>Postupy: reakce na ladicí program za běhu

Akce, které byste měli provést, když se zobrazí Just-in-Time dialogové okno ladicího programu závisí na co se pokoušíte provést:

#### <a name="if-you-want-to-fix-or-debug-the-error-visual-studio-users"></a>Pokud chcete opravit nebo ladění chyby (uživatelům aplikace Visual Studio)

- Musíte mít [nainstalovanou sadu Visual Studio](http://visualstudio.microsoft.com) Chcete-li zobrazit podrobné informace o této chybě a zkuste ho ladit. Další informace najdete v tématu [ladění pomocí ladicího programu za běhu](../debugger/debug-using-the-just-in-time-debugger.md). Pokud nelze vyřešit chyby a opravit aplikaci, obraťte se na vlastníka aplikace tuto chybu napravíme.

#### <a name="if-you-want-to-prevent-the-just-in-time-debugger-dialog-box-from-appearing"></a>Pokud chcete zabránit zobrazování dialogových oken ladicího programu za běhu

Můžete provést kroky, aby se zabránilo Just-in-Time ladicí program dialogové okno nezobrazovalo. Pokud aplikace zpracuje chybu, můžete tuto aplikaci spustit normálně.

1. (Webové aplikace) Pokud se pokoušíte spustit webovou aplikaci, můžete zakázat ladění skriptů.

    Pro Internet Explorer nebo Microsoft Edge zakážete ladění skriptů v dialogovém okně Možnosti Internetu. Dostanete z těchto nastavení **ovládací panely** > **síť a Internet** > **Možnosti Internetu** (přesný postup závisí na vaší verze Windows a prohlížeči).

    ![JITInternetOptions](../debugger/media/jitinternetoptions.png "JITInternetOptions")

    Znovu otevřete webovou stránku, kde jste našli chybu. Pokud toto nastavení problém nevyřeší, obraťte se na vlastníka webové aplikace k vyřešení problému.

3. (Uživatelům aplikace visual Studio) Pokud máte nainstalovanou sadu Visual Studio (nebo pokud jste měli dříve nainstalovaná a tento alias odebrali), [zakázání Just-in-Time ladění](../debugger/debug-using-the-just-in-time-debugger.md) a pokuste se znovu spusťte aplikaci.

    > [!IMPORTANT]
    > Pokud zakážete Just-in-Time ladění a aplikace dojde neošetřené výjimce (chyba), buď zobrazí se dialogové okno Standardní chyba místo nebo bude k chybě nebo zablokování aplikace. Aplikace se nespustí obvykle, dokud se nevyřeší chyby (podle vy nebo vlastník aplikace).

2. (Technologie ASP.NET a IIS) Pokud hostujete webové aplikace v ASP.NET ve službě IIS, zakážete ladění na straně serveru.

    Ve Správci služby IIS klikněte pravým tlačítkem na uzel serveru a zvolte **přepnout na zobrazení funkcí**. V části, ASP.NET, zvolte **kompilace .NET** a zkontrolujte, že zvolíte **False** jako chování ladění (postup se liší ve starších verzích služby IIS).

## <a name="see-also"></a>Viz také
 [Základy ladicího programu](../debugger/getting-started-with-the-debugger.md)
