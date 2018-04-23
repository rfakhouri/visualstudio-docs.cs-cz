---
title: Konfigurace brány Windows Firewall pro vzdálené ladění | Microsoft Docs
ms.custom: ''
ms.date: 05/18/2017
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 66e3230a-d195-4473-bbce-8ca198516014
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d9fdd6db229bf1aa6f607e096715ea485ec5c5ce
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/18/2018
---
# <a name="configure-the-windows-firewall-for-remote-debugging"></a>Konfigurace brány Windows Firewall pro vzdálené ladění
Toto téma popisuje postup konfigurace brány firewall pro povolení vzdáleného ladění na počítače, které používají následující operační systémy:  
  
-   Windows 10  
  
-   Windows 8 nebo 8.1  
  
-   Windows 7   
  
-   Windows Server 2012 R2  

-   Windows Server 2012
  
-   Windows Server 2008 R2 
  
 Pokud v síti, na kterém jsou ladění není chráněné bránou firewall, tato konfigurace je zbytečné. Počítač, který je hostitelem Visual Studio a vzdáleného počítače, který je chcete ladit, jinak hodnota vyžadovat změny konfigurace brány firewall.  
  
 **Protokol IPSec** Pokud síť vyžaduje tuto komunikaci se provádí pomocí protokolu IPSec, musíte otevřít další porty v sadě Visual Studio hostitelský počítač a vzdáleným počítačem.  
  
 **Webový Server** Pokud ladíte vzdálenému webovému serveru, musíte otevřít další port na vzdáleném počítači. (Pro službu IIS, je třeba port 80 otevřít.)  
  
 Všimněte si, že oba počítače, není nutné spustit stejný operační systém. Například počítač Visual Studio můžete spustit Windows 10 a vzdálený počítač můžete spustit Windows Server 2012 R2.      
  
## <a name="ports-on-the-remote-computer-that-enable-remote-debugging"></a>Porty na vzdáleném počítači, které povolení vzdáleného ladění  
  
|||||  
|-|-|-|-|  
|**Porty**|**Příchozí nebo odchozí**|**Protokol**|**Popis**|   
|4022|příchozí|TCP|Pro VS 2017. Číslo portu se zvýší o 2 pro každou verzi sady Visual Studio. Další informace najdete v tématu [Visual Studio vzdáleného ladicího programu Port přiřazení](../debugger/remote-debugger-port-assignments.md).|  
|4023|příchozí|TCP|Pro VS 2017. Číslo portu se zvýší o 2 pro každou verzi sady Visual Studio. (Jenom používá ke vzdálené ladění procesu 32-bit v 64bitové verzi vzdáleného ladicího programu.) Další informace najdete v tématu [Visual Studio vzdáleného ladicího programu Port přiřazení](../debugger/remote-debugger-port-assignments.md).| 
|3702|Odchozí|UDP|(Volitelné) Vyžaduje se pro zjišťování vzdáleného ladicího programu.|    
  
## <a name="how-to-configure-ports-in-windows-firewall"></a>Postup konfigurace portů v bráně Windows Firewall  

Při instalaci sady Visual Studio nebo vzdáleného ladicího programu software se pokusí otevřít správné porty. V některých případech (například pomocí brány firewall třetích stran), můžete však ručně otevřete port. Pokud je třeba ověřit, že jsou otevřené porty, přečtěte si téma [Poradce při potížích s](#troubleshooting). Některé pokyny k otevření portu se může lišit ve starších verzích systému Windows.

Chcete-li otevřít port:
  
1. Otevřete **spustit** nabídky, vyhledejte **brány Windows Firewall s pokročilým zabezpečením**.

2. Zvolte **příchozí pravidla > nové pravidlo > Port**a potom klikněte na **Další**. (Pro odchozí pravidla, vyberte **odchozí pravidla** místo.)

3. Vyberte buď **TCP** nebo **UDP**, v závislosti na číslo portu.

4. V části **určité místní porty**, zadejte číslo portu, klikněte na **Další**.

5. Klikněte na tlačítko **povolit připojení** a pak klikněte na **Další**.

6. Vyberte jeden nebo více typů sítě povolit pro port a klikněte na tlačítko **Další**.

    Typ, který jste vybrali musí zahrnovat sítě, ke které je připojený vzdáleného počítače.
7. Přidejte název (například **msvsmon**, **IIS**, nebo **Web Deploy**) pro pravidlo a klikněte na tlačítko **Dokončit**.

    Měli byste vidět nové pravidlo v seznamu pravidel příchozí nebo odchozí pravidla.

## <a name="troubleshooting"></a>Řešení potíží

Pokud máte potíže s vzdáleného ladicího programu se připojuje k vaší aplikace, musíte ověřit, že jsou otevřené správné porty.

### <a name="verify-that-ports-are-open-in-the-windows-firewall-on-the-visual-studio-computer"></a>Ověřte, zda jsou porty otevřít v bráně Windows Firewall v počítači Visual Studio  
 Pokyny ke konfiguraci brány Windows firewall se mírně liší v různých operačních systémech. V systému Windows 8 nebo 8.1, Windows 10 a Windows Server 2012, je slovo **aplikace** slouží; na Windows 7 nebo Windows Server 2008, je slovo **program** slouží;  V následujících krocích použijeme slovo **aplikace**.  
  
1.  Otevřete stránku brány Windows Firewall. (V **spustit** nabídky vyhledávacího pole, typ **brány Windows Firewall**).  
  
2.  Klikněte na tlačítko **povolit aplikace nebo funkci průchod bránou Windows Firewall**.  
  
3.  V **povolené aplikace a funkce** seznamu, vyhledejte **Visual Studio vzdáleného ladicího programu zjišťování**. Pokud je hodnota uvedena, ujistěte se, že je vybraná a že budou vybrány také jeden nebo více typů sítě.  
  
4.  Pokud **Visual Studio vzdáleného ladicího programu zjišťování** nejsou uvedeny, klikněte na tlačítko **povolit jinou aplikaci**. Pokud stále nevidíte v **přidat aplikaci** okně klikněte na tlačítko **Procházet** a přejděte do  **\<Visual Studio Instalační adresář > \Common7\IDE\Remoteladicíprogram**. Vyhledejte příslušnou složku pro aplikaci (x86, x64, Appx) a potom vyberte **msvsmon.exe**. Pak klikněte na tlačítko **přidat**.  
  
5.  V **povolené aplikace a funkce** seznamu, vyberte **Visual Studio Debugger vzdálené**. Zkontrolujte jeden nebo více typů sítě (**domény, domů a do práce (soukromý), veřejné**), které mají sledování vzdáleného ladění ke komunikaci s. Typy musí zahrnovat sítě, ke které je připojený počítač Visual Studio. 

### <a name="verify-that-ports-are-open-in-the-windows-firewall-on-the-remote-computer"></a>Ověřte, zda jsou porty otevřít v bráně Windows Firewall na vzdáleném počítači  
 Komponenty vzdáleného ladění můžete nainstalovat na vzdáleném počítači nebo spustit ze sdíleného adresáře. V obou případech musí být nakonfigurované brány firewall vzdáleného počítače. Vzdálené ladění součásti jsou umístěny v:  
  
 **\<Visual Studio Instalační adresář > \Common7\IDE\Remote ladicí program**  
  
 Pokyny ke konfiguraci brány Windows firewall se mírně liší v různých operačních systémech. V systému Windows 8 nebo 8.1, Windows 10 a Windows Server 2012, je slovo **aplikace** slouží; na Windows 7 nebo Windows Server 2008, je slovo **program** slouží;  V následujících krocích použijeme slovo **aplikace**.  
  
1.  Otevřete stránku brány Windows Firewall. (Na **spustit** nabídky vyhledávacího pole, typ **brány Windows Firewall**.)  
  
2.  Klikněte na tlačítko **povolit aplikace nebo funkci průchod bránou Windows Firewall**.  
  
3.  V **povolené aplikace a funkce** seznamu, vyhledejte **Visual Studio Debugger vzdálené**. Pokud je hodnota uvedena, ujistěte se, že je vybraná a že budou vybrány také jeden nebo více typů sítě.  
  
4.  Pokud **Visual Studio Debugger vzdálené** nejsou uvedeny, klikněte na tlačítko **povolit jinou aplikaci**. Pokud stále nevidíte v **přidat okna aplikace na**, klikněte na tlačítko **Procházet** a přejděte do  **\<Visual Studio Instalační adresář > \Common7\IDE\Remoteladicíprogram**. Vyhledejte příslušnou složku pro aplikaci (x86, x64, Appx) a potom vyberte **msvsmon.exe**. Pak klikněte na tlačítko **přidat**.  
  
5.  V **aplikace s povoleným** seznamu, vyberte **Visual Studio Debugger vzdálené**. Zkontrolujte jeden nebo více typů sítě (**domény, domů a do práce (soukromý), veřejné**), které mají sledování vzdáleného ladění ke komunikaci s. Typy musí zahrnovat sítě, ke které je připojený počítač Visual Studio. 

### <a name="managed-or-native-compatibility-mode-open-additional-ports-on-the-remote-computer"></a>(Režim kompatibility spravovaným nebo nativním) Otevřít další porty na vzdáleném počítači

Pokud používáte režim kompatibility v ladicím programu (**nástroje > Možnosti > ladění**), bude nutné otevřít další porty. Režim kompatibility umožňuje starší verzi ladicího programu a různé porty jsou povinné.

> [!NOTE]
> Starší verze ladicího programu je ladicího programu sady Visual Studio 2010.
  
|||||  
|-|-|-|-|  
|**Porty**|**Příchozí nebo odchozí**|**Protokol**|**Popis**|  
|135, 139, 445|Odchozí|TCP|Požadováno.|  
|137, 138|Odchozí|UDP|Požadováno.|  
|500, 4500|Odchozí|UDP|Vyžaduje, pokud zásady vaší domény vyžaduje síťové komunikace, které mají být provedeny prostřednictvím protokolu IPSec.|  
|80|Odchozí|TCP|Vyžaduje se pro ladění webového serveru.|
  
## <a name="see-also"></a>Viz také  
 [Vzdálené ladění](../debugger/remote-debugging.md)