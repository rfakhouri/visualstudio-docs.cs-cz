---
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.openlocfilehash: 26d9169be242990b9ca99b4fe4fe043d56fb7f30
ms.sourcegitcommit: 4d9c54f689416bf1dc4ace058919592482d02e36
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/19/2019
ms.locfileid: "58195866"
---
Je třeba mít na ladění vašeho kódu se symboly, které vytvoříte na počítači aplikace Visual Studio. Výkon vzdáleného ladícího programu je mnohem lépe při použití místní symboly.  Pokud je nutné použít vzdálené symboly, budete muset říct sledování vzdáleného ladění hledat symboly ve vzdáleném počítači.  

Od verze Visual Studio 2013 Update 2, vám pomůže následující msvsmon přepínač příkazového řádku pomocí vzdáleného symbolů pro spravovaný kód: `Msvsmon /FallbackLoadRemoteManagedPdbs`  

Další informace najdete v tématu nápovědy vzdáleného ladění (stisknutím klávesy **F1** v okně vzdáleného ladicího programu, nebo klikněte na tlačítko **Nápověda > využití**). Další informace najdete [.NET změny vzdálené načítání symbolů v sadě Visual Studio 2012 a 2013](http://blogs.msdn.com/b/visualstudioalm/archive/2013/10/16/net-remote-symbol-loading-changes-in-visual-studio-2012-and-2013.aspx)
