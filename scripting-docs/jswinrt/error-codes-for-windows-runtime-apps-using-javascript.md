---
title: "Kódy chyb pro aplikace Windows Runtime pomocí jazyka JavaScript | Microsoft Docs"
ms.custom: 
ms.date: 05/10/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: javascript
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- JavaScript, Windows Runtime error codes
- VS.WebClient.Help.APPHOST9601
- VS.WebClient.Help.APPHOST9602
- VS.WebClient.Help.APPHOST9603
- VS.WebClient.Help.APPHOST9604
- VS.WebClient.Help.APPHOST9605
- VS.WebClient.Help.APPHOST9606
- VS.WebClient.Help.APPHOST9607
- VS.WebClient.Help.APPHOST9608
- VS.WebClient.Help.APPHOST9610
- VS.WebClient.Help.APPHOST9611
- VS.WebClient.Help.APPHOST9613
- VS.WebClient.Help.APPHOST9614
- VS.WebClient.Help.APPHOST9615
- VS.WebClient.Help.APPHOST9616
- VS.WebClient.Help.APPHOST9617
- VS.WebClient.Help.APPHOST9618
- VS.WebClient.Help.APPHOST9619
- VS.WebClient.Help.APPHOST9620
- VS.WebClient.Help.APPHOST9623
- VS.WebClient.Help.APPHOST9624
- VS.WebClient.Help.APPHOST9626
ms.assetid: 4c6d4e90-602a-4b56-ae74-3458929da442
caps.latest.revision: "1"
author: erikadoyle
ms.author: edoyle
manager: jken
ms.openlocfilehash: 89b91a3246d0a6e2980459c2c35c7361168bccd4
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="error-codes-for-windows-runtime-apps-using-javascript"></a>Kódy chyb pro aplikace Windows Runtime pomocí jazyka JavaScript
Tady jsou kódy chyb zobrazují konzolou nástroje sady Microsoft Visual Studio při vývoji aplikace Windows Runtime pomocí jazyka JavaScript.
  
Chyba | Poznámky
----- | -------
APPHOST9601: "nelze načíst *remoteURI*. Aplikaci nelze načíst vzdálený webový obsah v místní kontextu." | Další informace o co je povolen v kontextu webové najdete v tématu [funkcí a omezení podle kontextu](https://msdn.microsoft.com/en-us/library/windows/apps/xaml/hh465373.aspx).
APPHOST9602: "" javascript:' je neplatnou hodnotou atributu a budou ignorovány. Nepoužívejte ' javascript:' identifikátory URI v kontextu místního. " | Z bezpečnostních důvodů nemůžete použít ' javascript:' identifikátory URI v místní kontextu. Další informace o co je povolen v kontextu místního najdete v tématu [funkcí a omezení podle kontextu](https://msdn.microsoft.com/en-us/library/windows/apps/xaml/hh465373.aspx).
APPHOST9603: "nelze načíst modul plugin ActiveX, který má ID třídy *atribut classID*.  Aplikace nelze načíst ovládací prvky ActiveX." | Aplikace Windows Runtime pomocí jazyka JavaScript nepodporuje vlastní ActiveXcontrols společnosti Microsoft. Pokud potřebujete ovládacího prvku uživatelského rozhraní, použijte ovládací prvek standardní webové ovládací prvky knihovny, nebo vytvořit vlastní ovládací prvek. Pokud potřebujete provést vlastní logiky, vytvořte vlastní objekt prostředí Windows Runtime. Informace o dalších HTML, CSS a JavaScript rozdíly najdete v tématu [funkce HTML, CSS a JavaScript a rozdíly](https://msdn.microsoft.com/en-us/library/windows/apps/xaml/hh465380.aspx).
APPHOST9604: "nejde přejít ke *uri* protože používá kódování neplatný znak.  Aplikace můžete přejít pouze na soubory s kódováním UTF8." | Všechny značky HTML, JavaScript a CSS získat přístup pomocí prostředí Windows Runtime musí být kódovaný jako formát transformace 8bitové Unicode (UTF-8). Informace o dalších HTML, CSS a JavaScript rozdíly najdete v tématu [funkce HTML, CSS a JavaScript a rozdíly](https://msdn.microsoft.com/en-us/library/windows/apps/xaml/hh465380.aspx).
APPHOST9605: "nejde přejít ke *targetURI* z *sourceURI* vzhledem k tomu, že cílový identifikátor URI je v zóně s vyšší zabezpečení. Nejde přejít ze zóny s nižší zabezpečení pro zónu s vyšší zabezpečení Pokud jste přejdete na lokální kontext URI z kontextu webové URI a jste registrováni lokální kontext identifikátor URI s metodou MSApp.addPublicLocalApplicationUri." | Další informace najdete v tématu [MSApp.addPublicLocalApplicationUri](https://msdn.microsoft.com/en-us/library/windows/apps/xaml/hh465759.aspx).
APPHOST9606: "nelze načíst *uri* protože používá připojení HTTP a ms-https připojení pouze element meta je k dispozici. Pouze připojení HTTPS jsou povoleny, pokud použijete element meta ms https připojení jen. Pomocí připojení HTTPS nebo, pokud nepotřebujete zabezpečené připojení, odeberte meta element." | Další informace najdete v tématu [jak vyžadovat připojení HTTPS](https://msdn.microsoft.com/en-us/library/windows/apps/xaml/hh452771.aspx).
APPHOST9607: "aplikaci se nemůžou spouštět v identifikátoru URI *uri* kvůli této chybě: *failureCode*." | Prostředek chybějící nebo neplatný soubor jsou běžné příčiny této chyby.
APPHOST9608: "aplikace nelze přejděte na o: prázdná stránka kvůli této chybě: *errorCode*." | 
APPHOST9610: "aplikace zjistil chybu při přípravě přejít na vlastní chybovou stránku: *errorCode*." |
APPHOST9611: "nelze aplikace přejděte na vlastní chybovou stránku kvůli této chybě: *errorCode*." |
APPHOST9613: "nelze aplikaci přejděte do * uri * kvůli této chybě: *errorCode*." | 
APPHOST9614: "dokumentu v rámci elementu iframe požadované *requestedDocMode* režimu dokumentů, ale systém vynucuje *currentDocMode* režimu dokumentů. Elementu iframe použije *currentDocMode* režimu dokumentů. " | Další informace o zobrazení vzdáleného webového obsahu najdete v tématu [způsob propojení na externí webové stránky](https://msdn.microsoft.com/en-us/library/windows/apps/xaml/hh780594.aspx).
APPHOST9615: "aplikace nemůže stáhnout soubor v *uri* vzhledem k tomu, že byl vyvolán prostřednictvím kódu programu mimo kontext místní." | Nastane, když obsah v kontextu webové pokusí stáhnout soubor prostřednictvím kódu programu.
APPHOST9616: "Tento identifikátor URI nelze použít informace o zeměpisné poloze rozhraní API.  Informace o zeměpisné poloze rozhraní API může být volána pouze z identifikátoru URI, který je součástí balíčku nebo je zahrnuta v elementu ApplicationContentUris manifest." | Další informace o co je povolen v kontextu webové najdete v tématu [funkcí a omezení podle kontextu](https://msdn.microsoft.com/en-us/library/windows/apps/xaml/hh465373.aspx).
APPHOST9617: "Tento identifikátor URI nelze použít rozhraní API schránky.  Schránky rozhraní API může být volána pouze z identifikátoru URI, který je součástí balíčku nebo je zahrnuta v elementu ApplicationContentUris manifest." | Další informace o co je povolen v kontextu webové najdete v tématu [funkcí a omezení podle kontextu](https://msdn.microsoft.com/en-us/library/windows/apps/xaml/hh465373.aspx).
APPHOST9618: "Tento identifikátor URI nelze použít window.close.  Metoda window.close nelze vyvolat jenom z zabalené obsah, který byl načten pomocí schématu identifikátoru URI ms-appx." | Další informace o co je povolen v kontextu webové najdete v tématu [funkcí a omezení podle kontextu](https://msdn.microsoft.com/en-us/library/windows/apps/xaml/hh465373.aspx).
APPHOST9619: "aplikace nejde přejít ke *uri* protože v kontextu webové stránky nesmí být nejvyšší úrovně dokumentu aplikace. Načtení stránky v elementu iframe místo." | Nejde přejít stránku nejvyšší úrovně na vzdálenou webovou stránku, ale aplikace může zobrazení webové stránky v [iframe](https://msdn.microsoft.com/en-us/library/ms535258(v=vs.85).aspx). Další informace o zobrazení vzdáleného webového obsahu najdete v tématu [způsob propojení na externí webové stránky](https://msdn.microsoft.com/en-us/library/windows/apps/xaml/hh780594.aspx).
APPHOST9620: "Tato aplikace se nezavřela, protože použije připojení HTTP a ms-https připojení pouze element meta je k dispozici. Pouze připojení HTTPS jsou povoleny, pokud použijete element meta ms https připojení jen. Použijte připojení HTTPS nebo, Pokud nevyžadujete zabezpečené připojení, odeberte meta element." | Další informace najdete v tématu [jak vyžadovat připojení HTTPS](https://msdn.microsoft.com/en-us/library/windows/apps/xaml/hh452771.aspx).
APPHOST9623: "nelze přeložit aplikaci *url* kvůli této chybě: *errorCode*." | Obvyklou příčinou této chyby je chybí soubor.  
APPHOST9624: "aplikace nelze načíst pomocí skriptu *adresa url* url protože adresu url spustí jinou aplikaci. Pouze přímou interakci můžete spustit jiné aplikaci." | Aplikace nemůže přímo spouštět další aplikace. Ostatní aplikace může být spuštěn uživatelem, pokud aplikace implementuje určité kontrakty. Další informace najdete v tématu [kontrakty aplikace a rozšíření](https://msdn.microsoft.com/en-us/library/windows/apps/xaml/hh464906.aspx).
APPHOST9626: "přímý odkaz na soubor prostředků `ms-appx://1d33240b-0b00-40e4-a416-a4750c48787f/ja-jp\images\logo.scale-140.png` byla zjištěna. Tento odkaz způsobí selhání při použití mimo ladění prostředí". | Z důvodu cesta k souboru `logo.scale-140.png`, tento soubor PNG je považován za lokalizovaný prostředek, který způsobil chybu v tom, že lokalizované prostředky nelze na něj odkazovat přímo. V tématu [globalizace aplikace (HTML)](https://msdn.microsoft.com/en-us/library/windows/apps/xaml/hh465006.aspx) Pokud máte v úmyslu použít tento soubor jako prostředek jazyk. Přejmenování adresáři problematické, jinak hodnota opakujte.
  
## <a name="see-also"></a>Viz také  
 [Pomocí prostředí Windows Runtime v jazyce JavaScript](../jswinrt/using-the-windows-runtime-in-javascript.md)