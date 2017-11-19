---
title: "Postupy: instalace předpokladů s aplikací ClickOnce | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-deployment
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- deploying applications [ClickOnce], prerequisites
- prerequisites, ClickOnce
- components, bootstrapping
ms.assetid: e964fca5-fdfd-47cf-a1c9-7fb96b1c88b5
caps.latest.revision: "13"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.openlocfilehash: 44acef520a15b86e15906eb4197f538b23b92d8a
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="how-to-install-prerequisites-with-a-clickonce-application"></a>Postupy: Instalace předpokladů s aplikací ClickOnce
Všechny [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace vyžadují v počítači je nainstalována správná verze rozhraní .NET Framework, ještě před jejich spuštěním; mnoho aplikací mít také další požadavky. Při publikování [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace, můžete sadu součásti, které mají být zabaleny společně s vaší aplikace. Během instalace se provede kontrolu pro každý požadavek k určení, pokud již existuje; Pokud nebude nainstalována před instalací [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace.  
  
 Namísto balení a publikování požadavky, můžete také zadat umístění pro stahování pro součásti. Například místo včetně požadavků ke každé aplikaci, kterou publikujete, můžete použít centrální sdílené složky nebo webovou adresu, která obsahuje instalační programy pro všechny vaše požadavky – během instalace, budou staženy součásti a nainstalovat z tohoto umístění.  
  
> [!IMPORTANT]
>  Měli byste přidat balíčky Instalační program požadovaných součástí na vývojovém počítači před publikováním první [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace. Další informace najdete v tématu [postup: zahrnují předpokladů s aplikací ClickOnce](../deployment/how-to-include-prerequisites-with-a-clickonce-application.md).  
  
 Požadavky jsou spravovány v **požadavky** dialogové okno, přístupný z **publikovat** podokně **Návrhář projektu**.  
  
> [!NOTE]
>  Kromě předem určený seznam požadovaných součástí můžete přidat vlastní komponenty do seznamu. Další informace najdete v tématu [vytváření balíčků zaváděcího nástroje](../deployment/creating-bootstrapper-packages.md).  
  
### <a name="to-specify-prerequisites-to-install-with-a-clickonce-application"></a>Chcete-li určit požadavky pro instalaci s aplikací ClickOnce  
  
1.  S projekt vybraný v **Průzkumníku řešení**na **projektu** nabídce klikněte na tlačítko **vlastnosti**.  
  
2.  Vyberte **publikovat** podokně.  
  
3.  Klikněte na tlačítko **požadavky** tlačítko Otevřít **požadavky** dialogové okno.  
  
4.  V **požadavky** dialogové okno pole, ujistěte se, že **vytvořit instalační program pro instalaci požadovaných součástí** je zaškrtnuté políčko.  
  
5.  V **požadavky** seznamu, zkontrolujte součásti, které chcete nainstalovat a potom klikněte na **OK**.  
  
     Vybrané součásti budou zabalené a publikovaná společně s vaší aplikace.  
  
### <a name="to-specify-a-different-download-location-for-prerequisites"></a>Chcete-li určit různá umístění pro předpoklady  
  
1.  S projekt vybraný v **Průzkumníku řešení**na **projektu** nabídce klikněte na tlačítko **vlastnosti**.  
  
2.  Vyberte **publikovat** podokně.  
  
3.  Klikněte na tlačítko **požadavky** tlačítko Otevřít **požadavky** dialogové okno.  
  
4.  V **požadavky** dialogové okno pole, ujistěte se, že **vytvořit instalační program pro instalaci požadovaných součástí** je zaškrtnuté políčko.  
  
5.  V **zadejte umístění instalace pro požadavky** vyberte **Stáhnout požadavky z následujícího umístění**.  
  
6.  Vyberte umístění v rozevíracím seznamu nebo zadejte adresu URL, cesta k souboru nebo umístění FTP a pak klikněte na tlačítko **OK.**  
  
    > [!NOTE]
    >  Musí se ujistěte, že instalační programy pro zadané součásti existují v zadaném umístění.  
  
## <a name="see-also"></a>Viz také  
 [Publikování aplikací ClickOnce](../deployment/publishing-clickonce-applications.md)   
 [Postupy: publikování aplikace ClickOnce pomocí Průvodce publikováním](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)