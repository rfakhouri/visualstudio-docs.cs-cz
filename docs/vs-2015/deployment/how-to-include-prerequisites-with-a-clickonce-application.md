---
title: 'Postupy: Zahrnutí předpokladů s aplikací ClickOnce | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-deployment
ms.topic: conceptual
ms.assetid: c66bf0a5-8c93-4e68-a224-3b29ac36fe4d
caps.latest.revision: 18
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: cdeb1b847b746807c80509f4390daf445f65d90f
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2019
ms.locfileid: "65697658"
---
# <a name="how-to-include-prerequisites-with-a-clickonce-application"></a>Postupy: Zahrnutí nezbytných součástí s aplikací ClickOnce
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Před distribucí požadovaného softwaru se [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] aplikace, musíte nejdřív stáhnout instalační balíčky pro tyto požadavky na vývojovém počítači. Když publikujete aplikaci a zvolte **stáhnout součásti ze stejného umístění, jako je má aplikace**, dojde k chybě, pokud instalační balíčky nejsou uloženy v **balíčky** složky.  
  
> [!NOTE]
> Přidání instalačního balíčku pro rozhraní .NET Framework naleznete v tématu [Průvodce nasazením rozhraní .NET Framework pro vývojáře](https://msdn.microsoft.com/library/ee942965\(v=vs.110\).aspx).  
  
## <a name="Package"></a> K přidání instalačního balíčku pomocí souboru Package.xml  
  
1. V Průzkumníku souborů otevřete **balíčky** složky.  
  
     Ve výchozím nastavení cesta je C:\Program Files\Microsoft Visual Studio 14.0\SDK\Bootstrapper\Packages na 32bitové verzi systému a C:\Program Files (x86) \Microsoft Visual Studio 14.0\SDK\Bootstrapper\Packages v 64bitovém systému.  
  
2. Otevřete složku požadovaného softwaru, který chcete přidat a potom otevřete složku jazyka nainstalované verze aplikace [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] (například **en** pro angličtinu).  
  
3. V poznámkovém bloku, otevřete **Package.xml** souboru.  
  
4. Vyhledejte **název** element, který obsahuje **http://go.microsoft.com/fwlink** a zkopírujte adresu URL. Zahrnout **LinkID** část.  
  
    > [!NOTE]
    > Pokud ne **název** obsahuje element **http://go.microsoft.com/fwlink** , otevřete **Product.xml** soubor v kořenové složce požadovaného softwaru a vyhledejte **fwlink** řetězec.  
  
    > [!IMPORTANT]
    > Některé požadované softwarové programy mohou mít několik instalačních balíčků (například v 32bitových nebo 64bitových systémech). Pokud je položek víc **název** elementy obsahovat **fwlink**, musí zopakovat zbývající kroky pro každý z nich.  
  
5. Vložte adresu URL do adresního řádku prohlížeče a pak po zobrazení výzvy ke spuštění nebo uložení, zvolte **Uložit**.  
  
     Tento krok stáhne instalační soubor do počítače.  
  
6. Zkopírujte soubor do kořenové složky požadovaného softwaru.  
  
     V případě požadovaného softwaru Windows Installer 4.5 zkopírujte soubor do složky \Packages\WindowsInstaller4_5.  
  
     Nyní můžete instalační balíček distribuovat spolu s aplikací.  
  
## <a name="see-also"></a>Viz také  
 [Postupy: Instalace nezbytných součástí aplikace ClickOnce](../deployment/how-to-install-prerequisites-with-a-clickonce-application.md)
