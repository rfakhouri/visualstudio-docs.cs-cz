---
title: '&lt;Podpis&gt; – Element (ClickOnce – nasazení) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- <Signature> element [ClickOnce deployment manifest]
ms.assetid: c99b07ad-e8ba-43f2-b0d6-3745e7a7c8b3
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload:
- multiple
ms.openlocfilehash: cae29bf7f1d5207258ddc90e7287f7fb3a3b2989
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="ltsignaturegt-element-clickonce-deployment"></a>&lt;Podpis&gt; – Element (ClickOnce – nasazení)
Obsahuje informace potřebné k digitálnímu podepisování tento – manifest nasazení.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      <Signature>   
   XML signature information   
</Signature>  
```  
  
## <a name="remarks"></a>Poznámky  
 Podepsání manifestu nasazení pomocí signatury obálky je nepovinný, ale nedoporučuje. Další informace o podepisování XML souborů najdete v článku World Wide Web Consortium, "Syntaxe a zpracování podpisu XML" popsaných v [ http://www.w3.org/TR/xmldsig-core/ ](http://www.w3.org/TR/xmldsig-core/).  
  
 Pokud chcete pro podepsání manifestu, musíte zadat hodnoty hash pro všechny soubory. Manifest se soubory, které nejsou s použitím algoritmu hash nelze podepsat, protože uživatelé nemůže ověřit obsah souborů bez hash hodnot.  
  
## <a name="example"></a>Příklad  
 Následující příklad kódu ukazuje `Signature` element v manifestu nasazení používá v [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] nasazení.  
  
```  
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