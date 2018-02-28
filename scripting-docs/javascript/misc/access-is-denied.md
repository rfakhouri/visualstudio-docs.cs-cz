---
title: "Přístup byl odepřen. | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology:
- javascript
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VS.WebClient.Help.SCRIPT5
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 8a512060-d744-47af-a83e-4ba42ea2c5b2
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
ms.openlocfilehash: 9c097cd09712d19acf5a0e4999b5c7a47469f958
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="access-is-denied"></a>Přístup byl odepřen.
Skript se pokusila o přístup k datům z jiného zdroje než hostitel aktuální stránky. Zásada stejného původu následuje Internet Exploreru a v dalších prohlížečích umožňuje skripty pro přístup k datům jenom z zdrojů pomocí stejné schéma, hostitele a portu adresy URL aktuální stránky.  
  
 Například pokud je aktuální stránka https://employees.mycompany.com, kterému nelze přistupovat data z následující adresy URL:  
  
-   http://data.contoso.com, protože používá protokol HTTP místo protokolu HTTPS.  
  
-   https://somedatasource.com, protože je jinou doménu.  
  
-   https://Employees.MyCompany.com:8888, protože ho používá jiný port.  
  
### <a name="to-correct-this-error"></a>Oprava této chyby  
  
-   Zjistěte, jestli podporuje rozhraní API, které se snažíte získat volání JSONP nebo CORS, která se používají dva přístupy, které bezpečně povolit skriptování mezi zdroji.  
  
-   Pokud se pro volání rozhraní API REST, Refaktorovat toto volání do kódu na straně serveru a potom vystavit nový koncový bod REST pro vaše skripty na straně klienta.  
  
     Další informace najdete v online dokumentaci týkající se zásada stejného původu, JSONP a CORS.