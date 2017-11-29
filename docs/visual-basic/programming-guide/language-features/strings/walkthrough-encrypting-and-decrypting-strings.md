---
title: "Şifreleme ve şifre çözme Visual Basic'de dizeleri"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- encryption [Visual Basic], strings
- strings [Visual Basic], encrypting
- decryption [Visual Basic], strings
- strings [Visual Basic], decrypting
ms.assetid: 1f51e40a-2f88-43e2-a83e-28a0b5c0d6fd
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: fd9ec8e7af771db3f042e08c8ab30f6ed5832c2b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-encrypting-and-decrypting-strings-in-visual-basic"></a><span data-ttu-id="4c7c3-102">İzlenecek yol: Visual Basic'de Dizeleri Şifreleme ve Şifresini Çözme</span><span class="sxs-lookup"><span data-stu-id="4c7c3-102">Walkthrough: Encrypting and Decrypting Strings in Visual Basic</span></span>
<span data-ttu-id="4c7c3-103">Bu kılavuz size nasıl kullanılacağını gösterir <xref:System.Security.Cryptography.DESCryptoServiceProvider> şifrelemek ve şifreleme hizmeti sağlayıcısı (CSP) Üçlü Veri şifreleme standardı sürümünü kullanarak dizeleri şifresini çözmek için sınıfı (<xref:System.Security.Cryptography.TripleDES>) algoritması.</span><span class="sxs-lookup"><span data-stu-id="4c7c3-103">This walkthrough shows you how to use the <xref:System.Security.Cryptography.DESCryptoServiceProvider> class to encrypt and decrypt strings using the cryptographic service provider (CSP) version of the Triple Data Encryption Standard (<xref:System.Security.Cryptography.TripleDES>) algorithm.</span></span> <span data-ttu-id="4c7c3-104">İlk adım, 3DES algoritmasını yalıtır ve base 64 kodlu bir dize şifrelenmiş verileri depolayan bir basit sarmalayıcı sınıfı oluşturmaktır.</span><span class="sxs-lookup"><span data-stu-id="4c7c3-104">The first step is to create a simple wrapper class that encapsulates the 3DES algorithm and stores the encrypted data as a base-64 encoded string.</span></span> <span data-ttu-id="4c7c3-105">Daha sonra bu sarmalayıcı güvenli bir şekilde bir genel olarak erişilebilir metin dosyasında özel kullanıcı verilerini depolamak için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="4c7c3-105">Then, that wrapper is used to securely store private user data in a publicly accessible text file.</span></span>  
  
 <span data-ttu-id="4c7c3-106">Kullanıcı parolaları (örneğin, parolalar) korumak ve kimlik bilgileri yetkisiz kullanıcılar tarafından okunmaz hale getirmek için şifreleme kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="4c7c3-106">You can use encryption to protect user secrets (for example, passwords) and to make credentials unreadable by unauthorized users.</span></span> <span data-ttu-id="4c7c3-107">Bu kullanıcının varlıkları korur ve takası sağlayan çalınmasını, gelen bir yetkili kullanıcı kimliği koruyabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="4c7c3-107">This can protect an authorized user's identity from being stolen, which protects the user's assets and provides non-repudiation.</span></span> <span data-ttu-id="4c7c3-108">Şifreleme, yetkisiz kullanıcılar tarafından erişilen bir kullanıcının verileri de koruyabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="4c7c3-108">Encryption can also protect a user's data from being accessed by unauthorized users.</span></span>  
  
 <span data-ttu-id="4c7c3-109">Daha fazla bilgi için bkz: [Şifreleme Hizmetleri](../../../../standard/security/cryptographic-services.md).</span><span class="sxs-lookup"><span data-stu-id="4c7c3-109">For more information, see [Cryptographic Services](../../../../standard/security/cryptographic-services.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="4c7c3-110">Daha fazla olduklarından Rijndael (artık Gelişmiş Şifreleme Standardı [AES] adlandırılır) ve Üçlü Veri Şifreleme Standardı (3DES) algoritmaları DES değerinden daha yüksek güvenlik sağlanabilmesi pkı'ya yoğun.</span><span class="sxs-lookup"><span data-stu-id="4c7c3-110">The Rijndael (now referred to as Advanced Encryption Standard [AES]) and Triple Data Encryption Standard (3DES) algorithms provide greater security than DES because they are more computationally intensive.</span></span> <span data-ttu-id="4c7c3-111">Daha fazla bilgi için bkz. <xref:System.Security.Cryptography.DES> ve <xref:System.Security.Cryptography.Rijndael>.</span><span class="sxs-lookup"><span data-stu-id="4c7c3-111">For more information, see <xref:System.Security.Cryptography.DES> and <xref:System.Security.Cryptography.Rijndael>.</span></span>  
  
### <a name="to-create-the-encryption-wrapper"></a><span data-ttu-id="4c7c3-112">Şifreleme sarmalayıcı oluşturmak için</span><span class="sxs-lookup"><span data-stu-id="4c7c3-112">To create the encryption wrapper</span></span>  
  
1.  <span data-ttu-id="4c7c3-113">Oluşturma `Simple3Des` şifreleme ve şifre çözme yöntemleri kapsülleyen sınıfı.</span><span class="sxs-lookup"><span data-stu-id="4c7c3-113">Create the `Simple3Des` class to encapsulate the encryption and decryption methods.</span></span>  
  
     [!code-vb[VbVbalrStrings#38](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_1.vb)]  
  
2.  <span data-ttu-id="4c7c3-114">Şifreleme ad alanı içe içeren dosyasının başlangıcına ekleyin `Simple3Des` sınıfı.</span><span class="sxs-lookup"><span data-stu-id="4c7c3-114">Add an import of the cryptography namespace to the start of the file that contains the `Simple3Des` class.</span></span>  
  
     [!code-vb[VbVbalrStrings#77](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_2.vb)]  
  
3.  <span data-ttu-id="4c7c3-115">İçinde `Simple3Des` sınıfı, 3DES şifreleme hizmeti sağlayıcısı depolamak için özel bir alan ekleyin.</span><span class="sxs-lookup"><span data-stu-id="4c7c3-115">In the `Simple3Des` class, add a private field to store the 3DES cryptographic service provider.</span></span>  
  
     [!code-vb[VbVbalrStrings#39](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_3.vb)]  
  
4.  <span data-ttu-id="4c7c3-116">Belirtilen anahtarı karma değerden belirtilen uzunlukta bir bayt dizisi oluşturur özel bir yöntem ekleyin.</span><span class="sxs-lookup"><span data-stu-id="4c7c3-116">Add a private method that creates a byte array of a specified length from the hash of the specified key.</span></span>  
  
     [!code-vb[VbVbalrStrings#41](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_4.vb)]  
  
5.  <span data-ttu-id="4c7c3-117">3DES şifreleme hizmeti sağlayıcısını başlatmak için bir oluşturucu ekleyin.</span><span class="sxs-lookup"><span data-stu-id="4c7c3-117">Add a constructor to initialize the 3DES cryptographic service provider.</span></span>  
  
     <span data-ttu-id="4c7c3-118">`key` Parametre denetimlerini `EncryptData` ve `DecryptData` yöntemleri.</span><span class="sxs-lookup"><span data-stu-id="4c7c3-118">The `key` parameter controls the `EncryptData` and `DecryptData` methods.</span></span>  
  
     [!code-vb[VbVbalrStrings#40](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_5.vb)]  
  
6.  <span data-ttu-id="4c7c3-119">Bir dize şifreler ortak bir yöntem ekleyin.</span><span class="sxs-lookup"><span data-stu-id="4c7c3-119">Add a public method that encrypts a string.</span></span>  
  
     [!code-vb[VbVbalrStrings#42](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_6.vb)]  
  
7.  <span data-ttu-id="4c7c3-120">Bir dize şifresini çözer ortak bir yöntem ekleyin.</span><span class="sxs-lookup"><span data-stu-id="4c7c3-120">Add a public method that decrypts a string.</span></span>  
  
     [!code-vb[VbVbalrStrings#43](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_7.vb)]  
  
     <span data-ttu-id="4c7c3-121">Sarmalayıcı sınıfı, kullanıcı varlıklarını koruma şimdi kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="4c7c3-121">The wrapper class can now be used to protect user assets.</span></span> <span data-ttu-id="4c7c3-122">Bu örnekte, güvenli bir şekilde bir genel olarak erişilebilir metin dosyasında özel kullanıcı verilerini depolamak için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="4c7c3-122">In this example, it is used to securely store private user data in a publicly accessible text file.</span></span>  
  
### <a name="to-test-the-encryption-wrapper"></a><span data-ttu-id="4c7c3-123">Şifreleme sarmalayıcı sınamak için</span><span class="sxs-lookup"><span data-stu-id="4c7c3-123">To test the encryption wrapper</span></span>  
  
1.  <span data-ttu-id="4c7c3-124">Ayrı bir sınıfta sarmalayıcının kullanan bir yöntem eklemek `EncryptData` bir dize şifrelemek ve kullanıcıya yazmak için yöntem kullanıcının Belgelerim klasörünü.</span><span class="sxs-lookup"><span data-stu-id="4c7c3-124">In a separate class, add a method that uses the wrapper's `EncryptData` method to encrypt a string and write it to the user's My Documents folder.</span></span>  
  
     [!code-vb[VbVbalrStrings#78](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_8.vb)]  
  
2.  <span data-ttu-id="4c7c3-125">Şifreli bir dize kullanıcıdan okuyan bir yöntem adı Belgelerim klasörünü ve sarmalayıcının dizesiyle şifresini çözer eklemek `DecryptData` yöntemi.</span><span class="sxs-lookup"><span data-stu-id="4c7c3-125">Add a method that reads the encrypted string from the user's My Documents folder and decrypts the string with the wrapper's `DecryptData` method.</span></span>  
  
     [!code-vb[VbVbalrStrings#79](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_9.vb)]  
  
3.  <span data-ttu-id="4c7c3-126">Arama için kullanıcı arabirimi kodu ekleyin `TestEncoding` ve `TestDecoding` yöntemleri.</span><span class="sxs-lookup"><span data-stu-id="4c7c3-126">Add user interface code to call the `TestEncoding` and `TestDecoding` methods.</span></span>  
  
4.  <span data-ttu-id="4c7c3-127">Uygulamayı çalıştırın.</span><span class="sxs-lookup"><span data-stu-id="4c7c3-127">Run the application.</span></span>  
  
     <span data-ttu-id="4c7c3-128">Uygulamayı test yanlış parola sağlarsanız, verilerin şifresi çözülmez olduğunu fark.</span><span class="sxs-lookup"><span data-stu-id="4c7c3-128">When you test the application, notice that it will not decrypt the data if you provide the wrong password.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c7c3-129">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="4c7c3-129">See Also</span></span>  
 <xref:System.Security.Cryptography>  
 <xref:System.Security.Cryptography.DESCryptoServiceProvider>  
 <xref:System.Security.Cryptography.DES>  
 <xref:System.Security.Cryptography.TripleDES>  
 <xref:System.Security.Cryptography.Rijndael>  
 [<span data-ttu-id="4c7c3-130">Şifreleme Hizmetleri</span><span class="sxs-lookup"><span data-stu-id="4c7c3-130">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)