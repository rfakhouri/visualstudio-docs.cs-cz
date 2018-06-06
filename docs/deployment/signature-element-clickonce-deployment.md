---
title: '&lt;Podpis&gt; – Element (ClickOnce – nasazení) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- <Signature> element [ClickOnce deployment manifest]
ms.assetid: c99b07ad-e8ba-43f2-b0d6-3745e7a7c8b3
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c02a7fb2ab17d5a8f8a8e141814be432a119bf82
ms.sourcegitcommit: 1b9c1e333c2f096d35cfc77e846116f8e5054557
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/06/2018
ms.locfileid: "34814957"
---
# <a name="ltsignaturegt-element-clickonce-deployment"></a>&lt;Podpis&gt; – Element (ClickOnce – nasazení)
Obsahuje informace potřebné k digitálnímu podepisování tento – manifest nasazení.  
  
## <a name="syntax"></a>Syntaxe  
  
```xml  
  
      <Signature>   
   XML signature information   
</Signature>  
```  
  
## <a name="remarks"></a>Poznámky  
 Podepsání manifestu nasazení pomocí signatury obálky je nepovinný, ale nedoporučuje. Další informace o podepisování souborů XML, najdete v článku World Wide Web Consortium, "Syntaxe a zpracování podpisu XML" popsaných v [ http://www.w3.org/TR/xmldsig-core/ ](http://www.w3.org/TR/xmldsig-core/).  
  
 Pokud chcete pro podepsání manifestu, musíte zadat hodnoty hash pro všechny soubory. Manifest se soubory, které nejsou s použitím algoritmu hash nelze podepsat, protože uživatelé nemůže ověřit obsah souborů bez hash hodnot.  
  
## <a name="example"></a>Příklad  
 Následující příklad kódu ukazuje `Signature` element v manifestu nasazení používá v [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] nasazení.  
  
```xml  
<Signature xmlns="http://www.w3.org/2000/09/xmldsig#">  
  <SignedInfo>  
    <CanonicalizationMethod Algorithm=  
           "http://www.w3.org/TR/2001/REC-xml-c14n-20010315" />  
    <SignatureMethod Algorithm=  
           "http://www.w3.org/2000/09/xmldsig#rsa-sha1" />  
    <Reference URI="">  
      <Transforms>  
        <Transform Algorithm=  
           "http://www.w3.org/2000/09/xmldsig#enveloped-signature" />  
      </Transforms>  
      <DigestMethod Algorithm="http://www.w3.org/2000/09/xmldsig#sha1" />  
      <DigestValue>d2z5AE...</DigestValue>  
    </Reference>  
  </SignedInfo>  
  <SignatureValue>  
4PHj6SaopoLp...  
  </SignatureValue>  
  <KeyInfo>  
    <X509Data>  
      <X509Certificate>  
MIIHnTCCBoWgAwIBAgIKJY9+nwAHAAB...  
      </X509Certificate>  
    </X509Data>  
  </KeyInfo>  
</Signature>  
```  
  
## <a name="see-also"></a>Viz také  
 [ClickOnce – manifest nasazení](../deployment/clickonce-deployment-manifest.md)