---
title: Emulátor sady Visual Studio pro Android | Microsoft Docs
ms.custom: ''
ms.date: 07/17/2017
ms.technology: vs-ide-mobile
ms.topic: conceptual
ms.assetid: 80f0104f-a4db-44dd-bd55-37bb67776c62
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 55e1e24a1482f40664d3f0c154d362c08bb9fa17
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="visual-studio-emulator-for-android"></a>Emulátor sady Visual Studio pro Android
Emulátor sady Visual Studio pro Android je plochy aplikace, která emuluje zařízení se systémem Android. Poskytuje virtualizované prostředí, ve kterém můžete ladění a testování aplikací pro Android bez fyzického zařízení. Poskytuje také izolované prostředí pro prototypy vaší aplikace.  

> [!IMPORTANT]
> Ve většině scénářů emulátor Google Android se doporučuje použít místo emulátor sady Visual Studio pro Android:
> - Pokud jste v emulátoru imagí obsahující Android 7.0 nebo novější, protože nejsou k dispozici žádný plán k publikování Android musí Image po verze 6.0 pro použití v emulátor sady Visual Studio pro Android.
> - Při použití nástroje sady Visual Studio pro Apache Cordova. Další informace najdete v tématu [spuštění aplikace Apache Cordova v Androidu](/visualstudio/cross-platform/tools-for-cordova/run-your-app/run-app-android#a-idgoogle-android-emulatora-run-on-the-google-android-emulator).
  
 Emulátor sady Visual Studio pro Android určená k poskytování porovnatelný z hlediska výkonu pouze pro skutečné zařízení. Před publikováním aplikace, ale doporučujeme, abyste otestovali vaši aplikaci ve fyzické zařízení.  
  
 Můžete otestovat vaši aplikaci ve profil jedinečný zařízení pro jednotlivé platformy Android, rozlišení obrazovky a další vlastnosti hardwaru nepodporuje Visual Studio Emulator for Android.
  
##  <a name="Installing"></a> Instalace a odinstalace  
 Instalace  
  
 Visual Studio Emulator for Android je součástí nástroje pro různé platformy, která je k dispozici v sadě Visual Studio a je možné nainstalovat během vlastní instalaci sady Visual Studio, když vyberete mobilní vývoj pro různé platformy, potom společné nástroje a Software Development Kit a emulátor pak Visual Studio pro Android.  
  
 Probíhá odinstalace  
  
 Můžete odinstalovat emulátor sady Visual Studio pro Android pomocí panelu Přidat nebo odebrat programy v Ovládacích panelech.  
  
> [!NOTE]
>  Odinstalace Visual Studio neodinstaluje emulátor. Emulátor je nutné odinstalovat samostatně.  
  
 Když odinstalujete emulátor sady Visual Studio pro Android, technologie Hyper-V virtuální sítě Ethernet adaptéry, které byly vytvořeny pro emulátor používat automaticky neodeberou. Tyto virtuální adaptéry (Pokud není používán) můžete odebrat ručně otevřete Správce technologie Hyper-V, vyberte jednu z imagí virtuálního pevného disku emulátoru, výběr karta síť a zvolením **odebrat** pro každý přepínač, které se zobrazí na této kartě.  
  
##  <a name="Requirements"></a> Požadavky na systém a zpětná kompatibilita  
 Důležité informace o hardwaru softwaru a požadavky na konfiguraci pro Visual Studio Emulator for Android, najdete v následujícím tématu.  
  
-   [Systémové požadavky pro emulátor sady Visual Studio pro Android](../cross-platform/system-requirements-for-the-visual-studio-emulator-for-android.md)  
  
 Visual Studio Emulator for Android vyžaduje Visual Studio 2015; není zpětně kompatibilní s předchozími verzemi sady Visual Studio.  
  
 Nové verze emulátoru jsou nainstalovány na staré verze (a v některých případech nahradit původní bitové kopie, zahození nastavení, aplikací a souborů nainstalovaných v těchto imagí).  
  
##  <a name="Networking"></a> Sítě v emulátor sady Visual Studio pro Android  
 Síťové připojení emulátor sady Visual Studio pro Android se chová jako připojení stolní počítač s těmito vlastnostmi:  
  
-   Emulátor zobrazí jako samostatné zařízení s vlastní IP adresu v síti.  
  
-   Nevyžaduje žádné další sítě software, který ještě není nainstalovaná v emulátoru.  
  
-   Není připojený k doméně systému Windows.  
  
 Pro pochopení možností v emulátoru síťové připojení, si ho přemýšlejte jako podobné připojení Wi-Fi z telefonu s Androidem ke stejné síti. Pokud aplikaci spuštěnou na váš telefon můžete přístupu k síťovým prostředkům přes připojení Wi-Fi, potom aplikace spuštěné v emulátoru dostupný také stejné síťovému prostředku.  
  
 Další informace o požadavky na síť, najdete v části [systémové požadavky pro emulátor sady Visual Studio pro Android](../cross-platform/system-requirements-for-the-visual-studio-emulator-for-android.md)  
  
 Informace o řešení potíží sítí, najdete v části [řešení potíží s Visual Studio Emulator for Android](../cross-platform/troubleshooting-the-visual-studio-emulator-for-android.md).  
  
##  <a name="Configuring"></a> Konfigurace emulátor sady Visual Studio pro Android  
 Testování vaší aplikace pro Android pro kompatibilitu mezi odstupňování řadu Android hardwaru může být složité. Android telefonů a tabletů na trhu span širokou škálu verze a velikost obrazovky a mají hardwarových konfigurací (paměti RAM, procesory, architektura atd.). Emulátor sady Visual Studio pro Android zjednodušuje, to pomocí profilů zařízení. Naše sady profilů zařízení představují nejoblíbenější hardwaru na trhu, včetně zařízení Samsung, Motorola, Sony, kontaktní skupině a další.  
  
 V sadě Visual Studio 2015 můžete instalovat, odinstalovat a spustit profily zařízení pomocí Správce emulátorů. Přístup správce emulátorů výběrem **nástroje**, pak **Visual Studio Emulator for Android**.  
  
 ![Emulátor sady Visual Studio pro Android Manager](../cross-platform/media/android_emu_manager.png "Android_Emu_Manager")  
  
 Ve výchozím nastavení, existují čtyři předem nainstalovaná zařízení profily (KitKat a typu Lupa phone/5 "a tablet/7" Konfigurace), jak je uvedeno bílý text a ikony. Další profily v seznamu zobrazí šedě, dokud se nerozhodnete **instalace profilu** tlačítko a instalace dokončí. Můžete filtrovat seznam podle úrovně rozhraní API a klikněte na šipku podrobnosti na pravé straně dolní profilu zobrazíte její podrobnosti úplná konfigurace.  
  
 Po instalaci sady profilů, které chcete zacílit, můžete tyto nové profily spustit přímo ze Správce stisknutím zeleným **přehrání** tlačítko. Také se zobrazí v rozevírací nabídce ladění cíl v žádný typ, a platformy mobilních projektu sady Visual Studio.  
  
##  <a name="FeaturesTest"></a> Funkce, které můžete testovat v emulátoru  
 Podrobné informace o funkcích můžete otestovat v emulátoru, najdete [příspěvku na blogu](http://blogs.msdn.com/b/visualstudioalm/archive/2014/11/12/introducing-visual-studio-s-emulator-for-android.aspx).  
  
##  <a name="FeaturesNonTest"></a> Funkce, které nelze otestovat v emulátoru  
 Následující seznam popisuje funkce platformu Android, které **nelze** testování v emulátoru. Je třeba otestovat tyto funkce na fyzické zařízení.  
  
-   Kompas  
  
-   Volný setrvačník  
  
-   Vibrace řadiče  
  
-   Také průraznost. Změna úrovně také průraznost emulátoru nebude mít vliv na vizuální způsob, jakým se zařízení objeví na obrazovce.  
  
##  <a name="Support"></a> Podpora prostředky  
 Pokud hostitelský počítač splňuje požadavky na systém a narazíte na problém nejsou zahrnuté v této příručce pro řešení potíží:  
  
-   Zeptejte se na StackOverflow pomocí [emulátoru android](http://stackoverflow.com/questions/tagged/android-emulator) a značky sady visual studio.  
  
-   Ohlásit problém pomocí odesílání nástroj smajlíka v sadě Visual Studio nebo ve Správci emulátor.  
  
## <a name="see-also"></a>Viz také  
 [Systémové požadavky pro emulátor sady Visual Studio pro Android](../cross-platform/system-requirements-for-the-visual-studio-emulator-for-android.md)   
 [Poradce při potížích s emulátorem sady Visual Studio pro Android](../cross-platform/troubleshooting-the-visual-studio-emulator-for-android.md)
