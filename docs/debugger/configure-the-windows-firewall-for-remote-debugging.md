---
title: Konfigurace brány Windows Firewall pro vzdálené ladění | Dokumentace Microsoftu
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
ms.openlocfilehash: 9688948ebe2fa5e045578ee808e068d59450d748
ms.sourcegitcommit: 80f9daba96ff76ad7e228eb8716df3abfd115bc3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/03/2018
ms.locfileid: "37433388"
---
# <a name="configure-the-windows-firewall-for-remote-debugging"></a>Konfigurace brány Windows Firewall pro vzdálené ladění
Toto téma popisuje postup konfigurace brány firewall pro povolení vzdáleného ladění na počítačích, na kterých běží tyto operační systémy:  
  
-   Windows 10  
  
-   Windows 8 nebo 8.1  
  
-   Windows 7   
  
-   Windows Server 2012 R2  

-   Windows Server 2012
  
-   Windows Server 2008 R2 
  
 Pokud v síti, na kterém jsou ladění není chráněné bránou firewall, tato konfigurace je zbytečné. V opačném případě počítače, který je hostitelem aplikace Visual Studio a vzdáleného počítače, který má být laděn vyžadovat změny konfigurace brány firewall.  
  
 **Protokol IPSec** Pokud síť vyžaduje tuto komunikaci se provádí pomocí protokolu IPSec, je nutné otevřít další porty na hostitelském počítači Visual Studio, tak vzdálenému počítači.  
  
 **Webový Server** Pokud ladíte vzdáleného webového serveru, je nutné otevřít další port na vzdáleném počítači. (Pro službu IIS, musí být port 80 otevřený.)  
  
 Všimněte si, že oba počítače nemají běžet stejný operační systém. Například v počítači s Visual Studio můžete spustit Windows 10 a vzdáleného počítače můžete spustit systém Windows Server 2012 R2.      
  
## <a name="ports-on-the-remote-computer-that-enable-remote-debugging"></a>Porty na vzdáleném počítači, které umožňují vzdálené ladění  
  
|**Porty**|**Příchozí/odchozí**|**Protokol**|**Popis**|   
|-|-|-|-|  
|4022|příchozí|TCP|Pro sady VS 2017. Číslo portu je zvýšen o 2 pro každou verzi sady Visual Studio. Další informace najdete v tématu [Visual Studio vzdálený ladicí program Port přiřazení](../debugger/remote-debugger-port-assignments.md).|  
|4023|příchozí|TCP|Pro sady VS 2017. Číslo portu je zvýšen o 2 pro každou verzi sady Visual Studio. (Pouze umožňují vzdálené ladění procesu 32-bit v 64bitové verzi vzdáleného ladicího programu.) Další informace najdete v tématu [Visual Studio vzdálený ladicí program Port přiřazení](../debugger/remote-debugger-port-assignments.md).| 
|3702|Odchozí|UDP|(Volitelné) Vyžaduje se pro zjišťování vzdálený ladicí program.|    
  
## <a name="how-to-configure-ports-in-windows-firewall"></a>Postup konfigurace portů v bráně Windows Firewall  

Při instalaci sady Visual Studio nebo vzdálený ladicí program, software se pokusí otevřít správné porty. Nicméně v některých případech (například použití brány firewall třetích stran), budete muset otevřít port ručně. Pokud je třeba ověřit, že jsou otevřené porty, přečtěte si téma [Poradce při potížích s](#troubleshooting). Některé pokyny k otevření portu se může lišit na starších verzích Windows.

Otevření portu:
  
1. Otevřít **Start** nabídky, vyhledejte **brány Windows Firewall s pokročilým zabezpečením**.

2. Klikněte na tlačítko **příchozí pravidla > nové pravidlo > portu**a potom klikněte na tlačítko **Další**. (Odchozí pravidla zvolte **odchozí pravidla** místo.)

3. Zvolte buď **TCP** nebo **UDP**, v závislosti na číslo portu.

4. V části **určité místní porty**, zadejte číslo portu, klikněte na tlačítko **Další**.

5. Klikněte na tlačítko **povolit připojení** a potom klikněte na tlačítko **Další**.

6. Vyberte jeden nebo více typů sítě pro povolení portu a klikněte na tlačítko **Další**.

    Typ, který jste vybrali musí zahrnovat sítě, ke kterému je připojený vzdáleného počítače.
7. Přidat název (například **msvsmon**, **IIS**, nebo **Webdeploy**) pro pravidlo a klikněte na tlačítko **Dokončit**.

    Měli byste vidět nové pravidlo v seznamu pravidel příchozí nebo odchozí pravidla.

## <a name="troubleshooting"></a>Řešení potíží

Pokud máte potíže s vzdálený ladicí program se připojuje k vaší aplikace, budete muset ověřit, že jsou otevřené správné porty.

### <a name="verify-that-ports-are-open-in-the-windows-firewall-on-the-visual-studio-computer"></a>Ověřte, že porty jsou otevřeny v bráně Windows Firewall počítače pro Visual Studio  
 Pokyny ke konfiguraci brány Windows firewall se mírně liší v různých operačních systémech. V systému Windows 8 a 8.1, Windows 10 a Windows Server 2012, slovo **aplikace** slouží; na Windows 7 nebo Windows Server 2008, slovo **program** slouží;  V následujícím postupu použijeme slovo **aplikace**.  
  
1.  Otevřete stránku brány Windows Firewall. (V **Start** nabídky vyhledávacího pole, typ **brány Windows Firewall**).  
  
2.  Klikněte na tlačítko **povolit aplikaci nebo funkci průchod bránou Windows Firewall**.  
  
3.  V **povolené aplikace a funkce** seznamu, vyhledejte **Visual Studio vzdálený ladicí program zjišťování**. Pokud je hodnota uvedena, ujistěte se, že je vybraná a že budou vybrány také jeden nebo více typů sítě.  
  
4.  Pokud **Visual Studio vzdálený ladicí program zjišťování** není uvedená, klikněte na **jiné aplikace bude**. Pokud stále nevidíte ji v **přidat aplikaci** okna, klikněte na tlačítko **Procházet** a přejděte do  **\<instalačního adresáře sady Visual Studio > \Common7\IDE\Remoteladicíhoprogramu**. Vyhledejte příslušnou složku pro aplikaci (x86, x64 Appx) a pak vyberte **msvsmon.exe**. Pak klikněte na tlačítko **přidat**.  
  
5.  V **povolené aplikace a funkce** seznamu vyberte **Visual Studio Remote Debugger**. Zkontrolujte jeden nebo více typů sítě (**domény, domů a do práce (privátní), veřejné**), který má sledování vzdáleného ladění pro komunikaci s. Typy musí zahrnovat sítě, ke kterému je připojený počítač Visual Studio. 

### <a name="verify-that-ports-are-open-in-the-windows-firewall-on-the-remote-computer"></a>Ověřte, že porty jsou otevřeny v bráně Windows Firewall na vzdáleném počítači  
 Komponenty vzdáleného ladění můžete nainstalovaný na vzdáleném počítači nebo spustit ze sdíleného adresáře. V obou případech musí být nakonfigurované brány firewall vzdáleném počítači. Komponenty vzdáleného ladění se nacházejí v:  
  
 **\<Visual Studio Instalační adresář > \Common7\IDE\Remote ladicího programu**  
  
 Pokyny ke konfiguraci brány Windows firewall se mírně liší v různých operačních systémech. V systému Windows 8 a 8.1, Windows 10 a Windows Server 2012, slovo **aplikace** slouží; na Windows 7 nebo Windows Server 2008, slovo **program** slouží;  V následujícím postupu použijeme slovo **aplikace**.  
  
1.  Otevřete stránku brány Windows Firewall. (Na **Start** nabídky vyhledávacího pole, typ **brány Windows Firewall**.)  
  
2.  Klikněte na tlačítko **povolit aplikaci nebo funkci průchod bránou Windows Firewall**.  
  
3.  V **povolené aplikace a funkce** seznamu, vyhledejte **Visual Studio Remote Debugger**. Pokud je hodnota uvedena, ujistěte se, že je vybraná a že budou vybrány také jeden nebo více typů sítě.  
  
4.  Pokud **Visual Studio Remote Debugger** není uvedená, klikněte na **jiné aplikace bude**. Pokud stále nevidíte ji v **přidat oknem aplikace**, klikněte na tlačítko **Procházet** a přejděte do  **\<instalačního adresáře sady Visual Studio > \Common7\IDE\Remoteladicíhoprogramu**. Vyhledejte příslušnou složku pro aplikaci (x86, x64 Appx) a pak vyberte **msvsmon.exe**. Pak klikněte na tlačítko **přidat**.  
  
5.  V **povolené aplikace** seznamu vyberte **Visual Studio Remote Debugger**. Zkontrolujte jeden nebo více typů sítě (**domény, domů a do práce (privátní), veřejné**), který má sledování vzdáleného ladění pro komunikaci s. Typy musí zahrnovat sítě, ke kterému je připojený počítač Visual Studio. 

### <a name="managed-or-native-compatibility-mode-open-additional-ports-on-the-remote-computer"></a>(Režim kompatibility spravované nebo nativní) Otevřít další porty na vzdáleném počítači

Pokud používáte režim kompatibility pro ladicí program (**nástroje > Možnosti > ladění**), bude nutné otevřít další porty. Režim kompatibility umožňuje starší verze ladicího programu a různé porty jsou povinné.

> [!NOTE]
> Starší verze ladicího programu je ladicí program sady Visual Studio 2010.
  
|**Porty**|**Příchozí/odchozí**|**Protokol**|**Popis**|  
|-|-|-|-|  
|135, 139, 445|Odchozí|TCP|Požadováno.|  
|137, 138|Odchozí|UDP|Požadováno.|  
|500, 4500|Odchozí|UDP|Povinné, pokud zásady vaší domény vyžadují síťové komunikace, která se má provést prostřednictvím protokolu IPSec.|  
|80|Odchozí|TCP|Vyžaduje se pro ladění webového serveru.|
  
## <a name="see-also"></a>Viz také  
 [Vzdálené ladění](../debugger/remote-debugging.md)