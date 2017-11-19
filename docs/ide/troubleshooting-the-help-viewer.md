---
redirect_url: /visualstudio/ide/microsoft-help-viewer
ms.openlocfilehash: c0b1a114eb157860dd70873929727cc56f1d6514
ms.sourcegitcommit: ec1c7e7e3349d2f3a4dc027e7cfca840c029367d
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/07/2017
---
Title: "řešení potíží s programu Help Viewer | Microsoft Docs"ms.custom:" "ms.date: ms.reviewer" 11/04/2016":" "ms.suite:" "ms.technology: 
  - ms.tgt_pltfrm "vs Prohlížeč nápovědy": "" ms.topic: "článku" helpviewer_keywords: 
  - "řešení potíží [Help Viewer]"
  - "Help Viewer, řešení potíží" ms.assetid: 461a4553-064a-4142-a2d2-058658b9ba12 caps.latest.revision: 13 Autor: ms.author "gewarren": "gewarren" správce: ghogen
---
# <a name="troubleshooting-the-help-viewer"></a>Řešení potíží s programem Help Viewer
Toto téma popisuje problémy, které se můžete setkat s prohlížeče nápovědy.  
  
## <a name="audio-doesnt-work"></a>Zvuk nefunguje.  
 Prohlížeč nápovědy neobsahuje zvuk přehrávač. Pokud si stáhnout obsah, který obsahuje zvuk a nic se stane, když zvolíte **přehrání**, nainstalujte zvuk přehrávač.  
  
## <a name="search-doesnt-work-in-windows-server-2008-windows-server-2008-with-sp1-or-windows-server-2008-r2"></a>Vyhledávání nefunguje v systému Windows Server 2008, Windows Server 2008 s aktualizací SP1 nebo Windows Server 2008 R2.  
 Funkce vyhledávání a filtrování v okně nápovědy, vyžadují instalaci služby Windows Search a na. Ve výchozím nastavení tato služba je vypnuto v systému Windows Server 2008, Windows Server 2008 s aktualizací Service Pack 1 (SP1) a Windows Server 2008 R2.  
  
#### <a name="to-activate-windows-search-service"></a>Chcete-li aktivovat hledání služby Windows  
  
1.  Spusťte správce serveru.  
  
2.  V levém navigačním podokně zvolte **role**.  
  
3.  V podokně Souhrn rolí vyberte **přidat roli**.  
  
4.  Zvolte role Souborové služby a potom **Další** tlačítko.  
  
5.  Vyberte službu role Windows Search.  
  
## <a name="additional-resources"></a>Další zdroje  
 Můžete získat další informace a poskytování zpětné vazby na Prohlížeč nápovědy pomocí následující prostředky:  
  
-   Chcete-li poskytnout zpětnou vazbu, přečtěte si téma [Microsoft Connect](http://go.microsoft.com/fwlink/?linkid=243983) na Microsoft Web nebo odesílání e-mailu o [ hlpfdbk@microsoft.com ](mailto:hlpfdbk@microsoft.com).  
  
-   Další informace, přejděte [dokumentaci pro vývojáře a systému nápovědy](http://go.microsoft.com/fwlink/?LinkId=232741) fórum.  
  
## <a name="see-also"></a>Viz také
[Příručka správce Help Vieweru](http://go.microsoft.com/fwlink/?LinkId=243985)