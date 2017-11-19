---
title: "Postupy: zahrnutí předpokladů s aplikací ClickOnce | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-deployment
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c66bf0a5-8c93-4e68-a224-3b29ac36fe4d
caps.latest.revision: "16"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.openlocfilehash: 18431ea15b53959234da4b2c6dedb24b8fa2e390
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="how-to-include-prerequisites-with-a-clickonce-application"></a>Postupy: Zahrnutí předpokladů s aplikací ClickOnce
Před distribucí požadovaný software s [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace, musíte nejprve stáhnout balíčky Instalační služby pro tyto požadavky na vývojovém počítači. Při publikování aplikace a zvolte **Stáhnout požadavky ze stejného umístění jako Moje aplikace**, dojde k chybě, pokud balíčky Instalační služby systému nejsou v **balíčky** složky.  
  
> [!NOTE]
>  Chcete-li přidat balíček Instalační služby pro rozhraní .NET Framework, najdete v části [rozhraní .NET Framework Průvodce nasazením pro vývojáře](http://msdn.microsoft.com/library/ee942965\(v=vs.110\).aspx).  
  
##  <a name="Package"></a>Chcete-li přidat balíček Instalační služby pomocí Package.xml  
  
1.  V Průzkumníku souborů, otevřete **balíčky** složky.  
  
     Ve výchozím nastavení cesta je C:\Program Files\Microsoft Visual Studio 14.0\SDK\Bootstrapper\Packages na 32bitovém systému a C:\Program Files (x86) \Microsoft Visual Studio 14.0\SDK\Bootstrapper\Packages na 64bitovém systému.  
  
2.  Otevřete složku pro požadavek, který chcete přidat a poté otevřete složku jazyk pro vaše nainstalovaná verze [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] (například **en** pro angličtinu).  
  
3.  V poznámkovém bloku otevřete **Package.xml** souboru.  
  
4.  Vyhledejte **název** elementu, který obsahuje **http://go.microsoft.com/fwlink**a zkopírujte adresu URL. Zahrnout **LinkID** část.  
  
    > [!NOTE]
    >  Pokud žádné **název** obsahuje element **http://go.microsoft.com/fwlink**, otevřete **Product.xml** souboru do kořenové složky pro požadované součásti a najděte  **fwlink** řetězec.  
  
    > [!IMPORTANT]
    >  Některé požadované softwarové programy mohou mít několik instalačních balíčků (například v 32bitových nebo 64bitových systémech). Pokud více **název** prvky obsahují **fwlink**, je nutné opakovat zbývající kroky pro každý z nich.  
  
5.  Vložte adresu URL do adresního řádku prohlížeče a potom, když se zobrazí výzva ke spuštění nebo uložení, vyberte **Uložit**.  
  
     Tento krok stáhne instalační soubor do počítače.  
  
6.  Zkopírujte soubor do kořenové složky požadovaného softwaru.  
  
     V případě požadovaného softwaru Windows Installer 4.5 zkopírujte soubor do složky \Packages\WindowsInstaller4_5.  
  
     Nyní můžete instalační balíček distribuovat spolu s aplikací.  
  
## <a name="see-also"></a>Viz také  
 [Postupy: instalace předpokladů s aplikací ClickOnce](../deployment/how-to-install-prerequisites-with-a-clickonce-application.md)