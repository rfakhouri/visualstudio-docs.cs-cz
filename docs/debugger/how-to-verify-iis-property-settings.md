---
title: 'Postupy: ověření nastavení vlastnosti služby IIS | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- IIS, property settings
- debugging Web applications, troubleshooting
- IIS administration tool
- Web applications, setting properties
- properties [debugger], setting with IIS administration tool
ms.assetid: 9efc50bf-02fb-4750-9b3e-f03c38f10d8b
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 2b351f45d8e45116894d08f4a813e7c427f4cb5c
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-verify-iis-property-settings"></a>Postupy: Ověření nastavení vlastnosti služby IIS
Můžete nastavit vlastnosti pro webovou aplikaci pomocí nástroje pro správu služby IIS. Tyto vlastnosti musí být správně nastavené pro aplikaci spustit, tak ověření těchto nastavení je často nezbytným krokem při řešení potíží.  
  
> [!NOTE]
>  Dialogová okna a příkazy nabídek, které vidíte, se mohou lišit od těch popsaných v nápovědě v závislosti na aktivních nastaveních nebo edici. Chcete-li změnit nastavení, zvolte **nastavení importu a exportu** na **nástroje** nabídky. Další informace najdete v tématu [přizpůsobení prostředí Visual Studio IDE](../ide/personalizing-the-visual-studio-ide.md).  
  
### <a name="to-check-iis-settings-for-the-web-application"></a>Zkontrolujte nastavení služby IIS pro webové aplikace  
  
1.  Otevřete **nástroje pro správu** okno: na **spustit** nabídky, přejděte na příkaz **programy**a potom klikněte na **nástroje pro správu**. Pokud **nástroje pro správu** v nezobrazí **programy** nabídky a podívejte se do **ovládací panely**.  
  
    -   V systému Windows 2000, vyberte **Správce služeb Internetu**.  
  
    -   V systému Windows XP, vyberte **Internetová informační služba**.  
  
    -   V systému Windows Server 2003, klikněte dvakrát na **Správa serveru**.  
  
         **Správa serveru** otevře se okno. V části **aplikační Server**, klikněte na tlačítko **správě tohoto serveru aplikace**.  
  
         **Aplikační Server** otevře se okno. Otevřete **Správce Internetové informační služby (IIS)** uzlu v levém podokně.  
  
2.  V dialogovém okně klikněte na řídicí uzel stromu pro váš počítač. Klikněte **weby** uzel a vyberte uzel webové aplikace. Buď bude uzel webu a proto na stejné úrovni jako **Default Web Site** uzlu, nebo virtuální adresář uzlu pod uzlu stávajícího webu.  
  
3.  Klikněte pravým tlačítkem na webové aplikace a v místní nabídce klikněte na tlačítko **vlastnosti**.  
  
4.  Ověřte nastavení zabezpečení pro webové aplikace:  
  
    1.  Ve webové aplikaci **vlastnosti** okně klikněte **zabezpečení adresáře** a klikněte na **upravit**.  
  
    2.  V **metody ověřování** dialogové okno, vyberte **povolit anonymní přístup** a **integrované ověřování systému Windows** Pokud ještě nejsou vybrána.  
  
    3.  Klikněte na tlačítko **OK** zavřete **metody ověřování** dialogové okno.  
  
5.  Pro aplikaci ATL Server ověřte, že je příkaz DEBUG přidružené rozšíření ISAPI. Další informace najdete v tématu [postup: přidružení ladění operaci s rozšířením](http://msdn.microsoft.com/en-us/50d261d3-4bd4-41c0-b44e-3591086f121e).  
  
6.  Pro [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] aplikace, zajistěte, aby virtuální složky pro aplikace, má název aplikace nastavit **Správce Internetové informační služby (IIS)**, **Správce služeb Internetu** nebo ** Internetová informační služba**.  
  
    1.  Ve webové aplikaci **vlastnosti** vyberte **Directory** kartě, pokud je aplikace ve virtuálním adresáři, nebo **domovský adresář** kartě, pokud je aplikace Webové stránky.  
  
    2.  Ověřte, že název v **místní cestu** odpovídá názvu adresáře, kde byla aplikace skutečně nasazeno.  
  
    3.  V části **nastavení aplikace**, zadejte název kořenového adresáře, která obsahuje aplikaci.  
  
    4.  Klikněte na tlačítko **OK** zavřete **vlastnosti** dialogové okno.  
  
7.  Pro [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] aplikace, klikněte na tlačítko **ASP.NET** kartě a ověřte, že správnou verzi [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] je zadán.  
  
8.  Klikněte na tlačítko **OK** zavřete **vlastnosti** dialogové okno.  
  
9. Klikněte na tlačítko **OK** zavřete **Správce Internetové informační služby (IIS)**, **Správce služeb Internetu**, nebo **Internetová informační služba**dialogové okno.  
  
## <a name="see-also"></a>Viz také  
 [Odstraňování potíží](../debugger/debugging-web-applications-troubleshooting.md)