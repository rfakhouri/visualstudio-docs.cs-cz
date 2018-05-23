---
title: 'Postupy: reakce na ladicí program za běhu | Microsoft Docs'
ms.custom: ''
ms.date: 05/23/17
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- debugging [Visual Studio], Just-In-Time
- Just-In-Time debugging
ms.assetid: 14972d5f-69bc-479b-9529-03b8787b118f
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 1b97e2d6b9ca269a86c3b66ffbcc4bb441051f29
ms.sourcegitcommit: b400528a83bea06d208d95c77282631ae4a93091
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/23/2018
---
# <a name="how-to-respond-to-the-just-in-time-debugger"></a>Postupy: reakce na ladicí program za běhu

Akce, které byste měli vzít až uvidíte pouze v době dialogové okno ladicí program závisí na co chcete udělat:

#### <a name="if-you-want-to-fix-or-debug-the-error-visual-studio-users"></a>Pokud chcete opravit nebo ladění chyb (Visual Studio uživatelů)

- Musíte mít [nainstalovanou sadu Visual Studio](http://www.visualstudio.com) Chcete-li zobrazit podrobné informace o chybě a pokusit se je ladění. Další informace najdete v tématu [ladění pomocí ladicího programu JIT](../debugger/debug-using-the-just-in-time-debugger.md). Pokud nelze vyřešit chyby a opravte aplikace, požádejte vlastníka aplikace opravte případné chyby.

#### <a name="if-you-want-to-prevent-the-just-in-time-debugger-dialog-box-from-appearing"></a>Pokud chcete zabránit zobrazování dialogových oken ladicího programu JIT

Můžete provést kroky, aby se zabránilo pouze v době ladicí program dialogové okno ze storu. Pokud aplikace zpracovává chyby, můžete aplikaci spustit normálně.

1. (Webové aplikace) Pokud se pokoušíte spustit webovou aplikaci, můžete zakázat ladění skriptů.

    Pro Internet Explorer nebo Microsoft Edge zakážete ladění skriptů v dialogovém okně Možnosti Internetu. Z těchto nastavení můžete přejít **ovládací panely** > **síť a Internet** > **Možnosti Internetu** (přesný postup závisí na vaší verze systému Windows a prohlížeč).

    ![JITInternetOptions](../debugger/media/jitinternetoptions.png "JITInternetOptions")

    Znovu otevřete webovou stránku, kde jste našli chyba. Pokud toto nastavení problém nevyřeší, obraťte se na vlastníka webové aplikace vyřešit problém.

3. (Uživatelé sady visual Studio) Pokud máte nainstalovanou sadu Visual Studio (nebo pokud bylo dřív nainstalované a odebrali), [ladění zakázat pouze za běhu](../debugger/debug-using-the-just-in-time-debugger.md) a pokuste se znovu spusťte aplikaci.

    > [!IMPORTANT]
    > Pokud zakážete těsně za běhu ladění a aplikace, dojde k neošetřené výjimce (chyba), budou buď zobrazit dialogové okno Standardní chyba místo nebo aplikace bude k chybě nebo zablokování. Aplikace se normálně nespustí, dokud se nevyřeší chyby (podle vy nebo vlastník aplikace).

2. (ASP.NET a IIS) Pokud hostujete ASP.NET webové aplikace ve službě IIS, zakážete ladění na straně serveru.

    Ve Správci služby IIS klikněte pravým tlačítkem na uzel serveru a zvolte **přepnout na zobrazení funkcí**. V části, ASP.NET, vyberte **kompilace rozhraní .NET** a ujistěte se, zvolíte **False** jako chování ladění (postup se liší v starší verze služby IIS).
  
## <a name="see-also"></a>Viz také    
 [Základy ladicího programu](../debugger/debugger-basics.md)   
