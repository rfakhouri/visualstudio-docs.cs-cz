---
title: "Řešení potíží s emulátor sady Visual Studio pro Android | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: tgt-pltfrm-cross-plat
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f3fb5df4-3aae-40e4-9450-bbe15b0c5af5
caps.latest.revision: "23"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6794bf2bbf53df5648c595d7a4ec47b30a974359
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="troubleshooting-the-visual-studio-emulator-for-android"></a>Poradce při potížích s emulátorem sady Visual Studio pro Android
Toto téma obsahuje informace k řešení problémů, které mohou nastat při použití emulátor sady Visual Studio pro Android.  
  
> [!WARNING]
>  Po nainstalování emulátoru, instalační program zkontroluje požadavky pro spuštění softwaru. Se zobrazí upozornění, pokud požadavky nejsou k dispozici, ale je není nutné pro instalaci.  
  
 Toto téma obsahuje následující části.  
  
-   [Než začnete](#BeforeYouStart)  
  
-   [Emulátor se instalace nezdaří.](#NoInstall)  
  
-   [Nelze se připojit k síti cíle v doméně nebo v podnikové síti](#DomainNetwork)  
  
-   [Nelze se připojit k síti cíle při vyžadují ruční konfiguraci nastavení sítě](#ManualNetworkConfig)  
  
-   [Emulátor spouští pomalu, nepodaří spustit z důvodu vypršení časového limitu nebo dojde k selhání nasazení aplikace](#SlowStart)  
  
-   [Emulátor nepodaří spustit](#NoStart2)  
  
-   [Emulátor nepodaří spustit (první použití)](#NoStart)  
  
-   [Počítač se nepodaří spustit po instalaci v emulátoru](#NoBoot)  
  
-   [Visual Studio vázne pokusu o nasazení aplikace na emulátoru nebo emulátoru se nezobrazí jako cíl ladění v jiných integrovaného vývojového prostředí](#ADB)  
  
-   [Emulátor přestane reagovat, protože nemohla nastavit UDP port](#XamarinPlayer)  
  
-   [Nelze připojit ladicí program k projektu Xamarin](#Skylake)  
  
-   [Emulátor nepodaří spustit aplikaci, která používá služby Google Play](#GooglePlay)  
  
-   [Přetažení souboru, APK nebo soubor zip si nefunguje](#DragAndDrop)  
  
-   [Řešení – snímek obrazovky je nesprávný](#Resolution)  
  
-   [Emulátor selže k vykreslení obsahu OpenGL](#OpenGL)  
  
-   [Emulátor neodpovídá na více touch gesta](#Multitouch)  
  
-   [Podpora prostředky](#Support)  
  
##  <a name="BeforeYouStart"></a>Než začnete  
 Než začnete řešit potíže, může být užitečné v následujících tématech:  
  
-   [Systémové požadavky pro emulátor sady Visual Studio pro Android](../cross-platform/system-requirements-for-the-visual-studio-emulator-for-android.md)  
  
##  <a name="NoInstall"></a>Emulátor se instalace nezdaří.  
 Pokud nemáte nainstalovanou technologií Hyper-v., zobrazí se následující zpráva při pokusu o nainstalujte si emulátor. Musí mít počítač, který podporuje Hyper-v a musí být povolena.  
  
 ![Android &#95; Měnové unie &#95; instalace &#95; problém](../cross-platform/media/android_emu_install_issue.png "Android_Emu_Install_Issue")  
  
> [!NOTE]
>  Tato zpráva platí jak pro emulátor sady Visual Studio pro Android a emulátoru Windows Phone. Windows 8.1 a Windows 10 podporovat emulátor.  
  
 Pokud se zobrazí tato zpráva, podívejte se [systémové požadavky pro emulátor sady Visual Studio pro Android](../cross-platform/system-requirements-for-the-visual-studio-emulator-for-android.md) zobrazíte, zda lze spustit emulátor.  
  
##  <a name="DomainNetwork"></a>Nelze se připojit k síti cíle v doméně nebo v podnikové síti  
 Emulátor sady Visual Studio pro Android se zobrazí jako samostatné zařízení pomocí jeho vlastní IP adresy v síti. Není připojen k doméně systému Windows a nesdílí přihlašovací údaje domény nebo pracovní skupiny s hostitelským počítačem.  
  
 Pokud síť vyžaduje ověření, domény nebo pracovní skupiny pro základní síť a připojení k Internetu, obraťte se na správce IT pro výjimku. Tato výjimka umožňuje vývojovém počítači, která bude sloužit jako počítač hranic a tak, aby přijímal připojení z domény nepřipojená síťová zařízení jako emulátor.  
  
 Emulátor sady Visual Studio pro Android také používá vlastní sadu adres MAC. Pokud z emulátoru serveru nemají přístup k síti nebo síťovým prostředkům na Internetu, obraťte se na správce IT a ujistěte se, že nebyl autorizován v emulátoru adresy MAC ve vaší síti.  
  
#### <a name="to-view-the-emulators-mac-addresses"></a>Chcete-li zobrazit v emulátoru MAC adres  
  
1.  Spusťte emulátor.  
  
2.  Na panelu nástrojů emulátor, klikněte na tlačítko s dvojitou šipkou (>>) a otevřete okno Další nástroje.  
  
3.  V okně dalších nástrojů klikněte na kartu sítě.  
  
4.  Na stránce sítě vyhledejte fyzickou adresu položky.  
  
##  <a name="ManualNetworkConfig"></a>Nelze se připojit k síti cíle při vyžadují ruční konfiguraci nastavení sítě  
 Pro připojení k síti cíle z emulátoru, musí vaše síť splňovat následující požadavky:  
  
-   DHCP. Emulátor vyžaduje DHCP, protože se konfiguruje jako samostatné zařízení v síti s vlastní IP adresu.  
  
-   Automaticky konfigurované DNS a nastavení brány. Není možné nakonfigurovat nastavení DNS a brány pro emulátor serveru ručně.  
  
 Pokud síť vyžaduje ručně nakonfigurované nastavení, obraťte se na správce IT k určení, jak můžete povolit připojení k síti pro emulátor.  
  
##  <a name="SlowStart"></a>Emulátor spouští pomalu, nepodaří spustit z důvodu vypršení časového limitu nebo dojde k selhání nasazení aplikace  
 Za určitých podmínek emulátoru trvá několik minut, spustit nebo nepodaří spustit z důvodu vypršení časového limitu. Když na emulátoru se nepodaří spustit, zobrazí se následující zpráva: `App deployment failed. Please try again`. Tato chyba může způsobit následující podmínky.  
  
-   Spuštění emulátor sady Visual Studio pro Android z spouštěcí virtuální pevný disk. Tato konfigurace není podporována.  
  
-   Vadný pevný disk. Vezměte v úvahu spuštění programu chkdsk.  
  
-   Pevný disk, který je potřeba defragmentovat. Vezměte v úvahu defragmentovat jednotku.  
  
-   Pevný disk, který je téměř plná. Kontrola místa na disku k dispozici.  
  
-   Z důvodu ostatní spuštěné aplikace je k dispozici není dostatek paměti. Snižte počet aplikací, které jsou spotřeba paměti nebo zvětšete velikost paměti.  
  
-   Obecně platí všechny faktor, který je přispívání do nízký výkon systému. Begin – řešení potíží s komponentou, který má nejnižší skóre v indexu prostředí systému Windows, kterou najdete na stránce informace o výkonu a nástrojů v Ovládacích panelech.  
  
##  <a name="NoStart2"></a>Emulátor nepodaří spustit  
 Pokud je emulátor byl dříve funguje, ale teď nefunguje, projít následující úlohy. Pokud používáte emulátor poprvé, přečtěte si téma [emulátoru nepodaří spustit (první použití)](#NoStart) před provedením těchto kroků.  
  
-   Odeberte všechny ostatní instance technologie Hyper-V emulátoru.  
  
    1.  Zavřete Visual Studio.  
  
    2.  Otevřete Správce technologie Hyper-V a zastavte všechny instance technologie Hyper-V emulátoru (virtuálních počítačů), který je již spuštěn a případně v poškozeném stavu.  
  
    3.  Ve Správci technologie Hyper-V odstraňte všechny ostatní emulátoru virtuálních počítačů.  
  
    4.  Po restartování počítače.  
  
-   Ujistěte se, že máte minimálně 4 GB systémové paměti a zda jej není spotřebovává další prostředky programy a procesy (např. Zkuste zavřít všechna okna prohlížeče).  
  
-   Ve Správci technologie Hyper-V otevřete Správce virtuálních přepínačů a zkontrolujte, že máte dvě síťové přepínače; Ověřte, zda interní přepínač je první a druhý je externí.  
  
     ![Android &#95; Měnové unie &#95; V &#95; Přepínač &#95; Man](../cross-platform/media/android_emu_v_switch_man.png "Android_Emu_V_Switch_Man")  
  
     Pokud je nesprávné nastavení a používáte Windows 10, může pokusit [přeinstalujte síťová zařízení pomocí příkazu -d netcfg](http://windows.microsoft.com/en-us/windows-10/fix-network-connection-issues) (část 6).  
  
-   Pokud tyto kroky problém nevyřeší, přečtěte si téma [emulátoru nepodaří spustit (první použití)](#NoStart) informace o 3. stran software, který může vadit pomocí emulátoru.  
  
##  <a name="NoStart"></a>Emulátor nepodaří spustit (první použití)  
 Pokud není možné spustit v emulátoru, projít následující úkoly a identifikovat a opravit potíže.  
  
-   Ujistěte se, že jsou splněny minimální požadavky na hardware a správnost nastavení systému BIOS.  
  
     Emulátor a Windows 8 Hyper-V vyžaduje 64bitový procesor s druhou překlad adres úrovně (SLAT). Pro technologii Intel musíte v podstatě základní i3 i5 nebo i7 procesoru (nebo jeden z mnoha Xeons). Seznam AMD čipy je k dispozici [zde](http://support.amd.com/en-us).  
  
    1.  Zkontrolujte, že počítač splňuje [požadavky na systém](../cross-platform/system-requirements-for-the-visual-studio-emulator-for-android.md).  
  
    2.  Ověřte, zda [SLAT nástroj](https://slatstatuscheck.codeplex.com/) hlásí, že je váš počítač podporuje technologii SLAT.  
  
    3.  V nastavení systému BIOS počítače Ujistěte se, zda je povoleno všechny virtualizační technologie. Přesné popisy systému BIOS se může lišit pro každého výrobce hardwaru. Obecně platí povolení funkce související s:  
  
        -   SLAT (druhé úrovně překlad adres)  
  
        -   Přijmout (Extended Page Tables) (Intel)  
  
        -   NPT (vnořené Page Tables) (AMD)  
  
        -   RVI (rychlé virtualizace indexování) (AMD)  
  
        -   VMX (zkratka Intel označující podpora virtualizace s hardwarovým řízením)  
  
        -   SVM (zkratka AMD označující podpora virtualizace s hardwarovým řízením)  
  
        -   XD (provést zakázání) (Intel); musí být povoleno  
  
        -   NX (žádné Execute)(AMD); Toto musí být povolena.  
  
    4.  Pokud jsou následující možnosti v systému BIOS, je zakážete.  
  
        -   Zakázat Intel VT-d  
  
        -   Zakázat Trusted Execution  
  
         Další informace najdete v tomto článku: Technet: jak Hyper-V: na opravte systému BIOS chyby povolení Hyper-V  
  
    5.  Ujistěte se, že máte minimálně 4 GB systémové paměti a zda jej není spotřebovává další prostředky programy a procesy.  
  
    6.  Ujistěte se, že používáte systém Windows 8 Professional nebo lepší (Windows Server 2008 není podporována.). Windows Server 2012 je podporována, ale je nutné povolit možnosti práce s počítačem.  
  
     Si můžete prohlédnout v prohlížeči událostí, zda jsou všechny chyby hypervisoru. Chcete-li to provést, otevřete Prohlížeč událostí (počáteční klíč + R a pak zadejte `eventvwr`) a potom vyberte **protokoly systému Windows**, **systému**. Vyfiltrujte v protokolu podle zdroje události nastavení zdroji na **technologie Hyper-V-hypervisoru**. Vyhledejte chyby, aby bylo možné identifikovat hlavní příčinu.  
  
     Pokud vaše procesoru splňuje minimální požadavky, ale hypervisor stále nedaří, zvažte, hledání se v případě upgradu systému BIOS k dispozici je pro tento počítač. Pokud existuje, a rozhodnete upgradovat, je nutné sledovat všechny opatření od výrobce, při upgradu systému BIOS (například tím, že upgrade firmwaru systému BIOS není přerušena při výpadku napájení, které může trvale dojít k poškození systému BIOS).  
  
-   Ujistěte se, že máte minimálně 4 GB systémové paměti a zda jej není spotřebovává další prostředky programy a procesy.  
  
-   Odebrat nebo zakázat ovladače třetích stran nebo software, který může být zasahovala do virtuální sítě.  
  
     Existují některé známé problémy s produkty některé 3. stran nainstalovaná v systému Windows 8 například síťové ovladače nebo protokoly, které nejsou plně kompatibilní s technologií Hyper-V síťových protokolů.  
  
     Obecně platí bude až vývojářům tyto produkty se aktualizace softwaru pro zajištění kompatibility s Windows 8 a technologie Hyper-V.  
  
     Následující produkty může vyžadovat upgradování pro dodržování předpisů pro Windows 8: VirtualBox, virtuální počítače VMWare, 7 někteří klienti VPN software brány firewall, některé verze klientů Cisco VPN a jiných systémů virtualizace. Spolupracovat s vývojáři sporná virtualizační software na podporu, aby aktualizace softwaru, aby byl kompatibilní s Windows 8 a technologie Hyper-V.  
  
     Jako **alternativní řešení**, zakážete všechny ovladače jiných výrobců a aplikace, které může být zasahovala do virtuální sítě pomocí emulátoru komunikovat pomocí sady Visual Studio. Tyto aplikace mohou zahrnovat:  
  
    -   Antivirové aplikace (které připojit do sady síťových protokolů)  
  
    -   Nástroje pro monitorování sítě  
  
    -   Nástroje protokolování  
  
    -   Další software monitorování systému  
  
     Jiné možných alternativních souborem odinstalaci produktů v otázku (a požaduje produktu vývojáře k uvolnění aktualizovaná verze), je pomocí následujících kroků.  
  
    1.  Spusťte Správce připojení k síti (na obrazovce Start zadejte `View Network Connections` a vybrat tuto možnost, chcete-li zobrazit síťová připojení.)  
  
    2.  Pro adaptér vEthernet (interní Port Windows Phone emulátoru interní přepínač Ethernet), zvolte **vlastnosti** v místní nabídce.  
  
         ![Virtuální adaptér používá Hyper & č. 45; V](../cross-platform/media/android_emu_virtual_adapter.png "Android_Emu_Virtual_Adapter")  
  
         Zde se zobrazují vlastnosti adaptéru.  
  
         ![Vlastnosti virtuálního adaptéru](../cross-platform/media/android_emu_virtual_adapter_properties.png "Android_Emu_Virtual_Adapter_Properties")  
  
    3.  Pro tento adaptér se pouze položky, které je nutné vybrat v rámci **toto připojení používá následující položky** by měl být následující:  
  
        -   Klient sítě Microsoft  
  
        -   Plánovač paketů technologie QoS  
  
        -   Sdílení souborů a tiskáren v sítích Microsoft  
  
        -   Ovladač Microsoft LLDP protokolu  
  
        -   Ovladač vstupně-výstupních operací mapovače zjišťování topologie linkové vrstvě  
  
        -   Odpovídající zařízení zjišťování topologie linkové vrstvě  
  
        -   Internet Protocol Version 6 (TCP/IPv6)  
  
        -   Internet Protocol verze 4 (TCP/IPv4)  
  
    4.  Zrušte výběr další položky.  
  
     Nevýhodou použití Tato technika je, že kdykoli a nové 3. stran produkt instaluje nepodporované ovladače nebo kdykoli nainstalování emulátoru těchto kroků bude nutné opakovat.  
  
     Po odinstalování produkty třetích stran musíte obnovit interní přepínač emulátoru Windows Phone. Postup:  
  
    -   Otevřete Hyper V a přejděte do Správce virtuálního přepínače. Vytvořit virtuální přepínač s názvem "Windows Phone emulátoru interní přepínač" a nastavte její typ připojení na **interní síti**.  
  
         ![Správce virtuálního přepínače](../cross-platform/media/android_emu_virtual_switch_manager.png "Android_Emu_Virtual_Switch_Manager")  
  
     Nyní spusťte emulátor. By se měly fungovat.  
  
##  <a name="NoBoot"></a>Počítač se nepodaří spustit po instalaci v emulátoru  
 Tomuto problému může dojít, když jsou splněné následující podmínky:  
  
-   V počítači je základní desky gigabajt.  
  
-   USB3 je povoleno na základní desce.  
  
 Chcete-li tento problém vyřešit, zakažte USB3 v nastavení systému BIOS základní desky a restartujte počítač. Potom zkontrolujte, zda gigabajt vydala aktualizaci systému BIOS základní desky.  
  
 Další informace najdete v následujícím článku znalostní báze Knowledge Base: [spouštěcí selhání po instalaci role Hyper-V v systémech gigabajt](https://support.microsoft.com/en-us/kb/2693144).  
  
##  <a name="ADB"></a>Visual Studio vázne pokusu o nasazení aplikace na emulátoru nebo emulátoru se nezobrazí jako cíl ladění v jiných integrovaného vývojového prostředí  
 Pokud emulátoru běží, ale nezobrazí k připojení k ADB (Android ladění mostu) nebo v nástroje pro Android, které využívají ADB (například Android Studio nebo Eclipse) nezobrazí, můžete upravit, kde emulátoru hledá ADB. Emulátor používá k určení základní umístění Android SDK klíč registru a hledá soubor \platform-tools\adb.exe v tomto adresáři. Úprava cesta k Android SDK používaná emulátorem:  
  
-   Otevřete Editor registru tak, že vyberete **spustit** z místní nabídky Start tlačítka zadáním `regedit` v dialogovém okně a výběr **OK**.  
  
-   Ve stromové struktuře složek na levé straně přejděte na HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Android SDK Tools.  
  
-   Změnit **cesta** registru proměnné tak, aby odpovídaly cestu k Android SDK.  
  
 Restartujte emulátoru a byste měli nyní uvidí emulátor připojen k ADB a související nástroje pro Android.  
  
##  <a name="XamarinPlayer"></a>Emulátor přestane reagovat, protože nemohla nastavit UDP port  
 Tento problém z důvodu nekompatibility s nástrojem Xamarin Player může dojít. Pokud se zobrazí emulátor přestane reagovat nebo pokud se zobrazí tato chybová zpráva "nelze se připojit k operační systém zařízení je emulátor: nemohla nastavit UDP port.  Může se zakázat některé funkce", může se jednat tento problém. Proveďte následující kroky.  
  
1.  Odinstalujte Xamarin Player.  
  
2.  Ověřte, zda že bylo dané pole virtuální odebrané (Xamarin Player běží nad virtuální pole).  
  
3.  Přejděte do Správce zařízení, vyberte možnost Zobrazit skrytá zařízení a pak odstraňte všechno kromě fyzických síťových karet.  
  
4.  Můžete zkusit odinstalovat nebo přeinstalovat technologie Hyper-V po odebrání všech jiných fyzických síťových adaptérech.  
  
##  <a name="Skylake"></a>Nelze připojit ladicí program k projektu Xamarin  
 Pokud používáte Windows 10 s procesory Intel Skylake, aplikace Xamarin se nemusí podařit spustit v emulátoru nebo ladicího programu sady Visual Studio nemusí připojit k nim. To je kvůli problému s technologií Hyper-V a Skylake procesory. Jako alternativní řešení proveďte následující kroky.  
  
1.  Otevřete Správce technologie Hyper-V a vyberte virtuální počítač pro emulátor profilu, který vaše jsou pomocí.  
  
2.  Vyberte **odstranit uložená stav** (vpravo dole).  
  
3.  Zvolte **nastavení...**  
  
4.  Rozbalte uzel procesoru a zvolte **kompatibility**.  
  
5.  Povolit **migrovat do fyzického počítače s jinou verzí procesoru**.  
  
6.  Restartujte službu (v části **akce**) a zkuste to znovu.  
  
##  <a name="GooglePlay"></a>Emulátor nepodaří spustit aplikaci, která používá služby Google Play  
 Emulátor se nedodává s knihovny služby Google Play. Emulátor však podporuje přetahování myší instalaci si zip souborů.  
  
##  <a name="DragAndDrop"></a>Přetažení souboru, APK nebo soubor zip si nefunguje  
 Emulátor používá ADB.exe usnadňuje přenos souborů, když jste přetažení soubor na obrazovku. Pokud dojde k chybě při pokusu o přetažení soubor, pravděpodobně označuje, že je emulátor není připojen k ADB.exe. Pokud chcete vyřešit, postupujte podle kroků v [Visual Studio vázne pokusu o nasazení aplikace na emulátoru nebo emulátoru se nezobrazí jako cíl ladění v jiných integrovaného vývojového prostředí](#ADB).  
  
##  <a name="Resolution"></a>Řešení – snímek obrazovky je nesprávný  
 Pokud pořídíte snímek pomocí kartě – snímek obrazovky v **další nástroje** okno a výsledný obraz má neočekávanou velikost, budete muset upravit úroveň přiblížení obrazovky před volbou **zaznamenat**. Emulátor načítá snímky obrazovky na rozlišení obrazovky na monitoru počítače hostitele.  
  
##  <a name="OpenGL"></a>Emulátor selže k vykreslení obsahu OpenGL  
 Emulátor vykreslí obsah OpenGL pomocí GPU hostitelský počítač a používá projektu úhel k převedení těchto volání z rozhraní DirectX. Pokud vaše aplikace vykreslí správně na zařízení ale nesprávně v emulátoru, je pravděpodobné, že zařízení je zmírnění nesprávné volání OpenGL (například pomocí shaderu proměnné, které neodpovídají).  
  
##  <a name="Multitouch"></a>Emulátor neodpovídá na více touch gesta  
 V některých případech emulátoru spustí a nereaguje na více touch buď přes přímé interakce z dotykového displeje nebo pomocí nástroje více Touch na panelu nástrojů emulátor. Pokud je to tento případ, vyberte **otočit** tlačítka na panelu nástrojů emulátoru a pokus o použití více touch znovu. Pokud problém přetrvává, přečtěte si [emulátoru selže k vykreslení obsahu OpenGL](#OpenGL) problém.  
  
##  <a name="Support"></a>Podpora prostředky  
 Pokud hostitelský počítač splňuje požadavky na systém a narazíte na problém nejsou zahrnuté v této příručce pro řešení potíží:  
  
-   Zeptejte se na StackOverflow pomocí [emulátoru android](http://stackoverflow.com/questions/tagged/android-emulator) a visual studio.  
  
-   Ohlásit problém pomocí odesílání nástroj smajlíka v sadě Visual Studio nebo ve Správci emulátor.