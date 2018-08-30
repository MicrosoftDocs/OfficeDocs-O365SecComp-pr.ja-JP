---
title: Office 365 の証明書チェーン
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/26/2018
ms.audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
ms.assetid: 0c03e6b3-e73f-4316-9e2b-bf4091ae96bb
description: Office 365 は、別の証明書のプロバイダーを利用しています。お客様が Office 365 にアクセスするときに発生可能性のある既知の Office 365 ルート証明書の完全な一覧を次に示します。証明書については、独自のインフラストラクチャのインストール、Office 365 のサード パーティの SSL 証明書の計画を参照してくださいする必要があります。次の証明書情報は、Office 365 のすべての国内世界的なクラウドのインスタンスに適用されます。
ms.openlocfilehash: 1dcc2dc38bb8e3239a3be3983791b0c60917dc5e
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532032"
---
# <a name="office-365-certificate-chains"></a><span data-ttu-id="a138a-106">Office 365 の証明書チェーン</span><span class="sxs-lookup"><span data-stu-id="a138a-106">Office 365 Certificate Chains</span></span>

<span data-ttu-id="a138a-p102">Office 365 は、別の証明書のプロバイダーを利用しています。お客様が Office 365 にアクセスするときに発生可能性のある既知の Office 365 ルート証明書の完全な一覧を次に示します。証明書については、独自のインフラストラクチャをインストールする必要があります、 [Office 365 の SSL 証明書をサード ・ パーティの計画](https://support.office.com/article/b48cdf63-07e0-4cda-8c12-4871590f59ce)を参照してください。次の証明書情報は、Office 365 のすべての国内世界的なクラウドのインスタンスに適用されます。</span><span class="sxs-lookup"><span data-stu-id="a138a-p102">Office 365 leverages a number of different certificate providers. The following describes the complete list of known Office 365 root certificates that customers may encounter when accessing Office 365. For information on the certificates you may need to install in your own infrastructure, see [Plan for third-party SSL certificates for Office 365](https://support.office.com/article/b48cdf63-07e0-4cda-8c12-4871590f59ce). The following certificate information applies to all worldwide and national cloud instances of Office 365.</span></span>
  

|<span data-ttu-id="a138a-111">**証明書の種類**</span><span class="sxs-lookup"><span data-stu-id="a138a-111">**Certificate type**</span></span>|<span data-ttu-id="a138a-112">**P7b ダウンロード**</span><span class="sxs-lookup"><span data-stu-id="a138a-112">**P7b download**</span></span>|<span data-ttu-id="a138a-113">**CRL の端点**</span><span class="sxs-lookup"><span data-stu-id="a138a-113">**CRL Endpoints**</span></span>|<span data-ttu-id="a138a-114">**OCSP の端点**</span><span class="sxs-lookup"><span data-stu-id="a138a-114">**OCSP Endpoints**</span></span>|<span data-ttu-id="a138a-115">**AIA の端点**</span><span class="sxs-lookup"><span data-stu-id="a138a-115">**AIA Endpoints**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="a138a-116">信頼関係のルート証明書の公開</span><span class="sxs-lookup"><span data-stu-id="a138a-116">Publicly Trusted Root Certificates</span></span>](https://support.office.com/article/0c03e6b3-e73f-4316-9e2b-bf4091ae96bb#rootcerts) <br/> |[<span data-ttu-id="a138a-117">Office 365 のルート証明書バンドル (P7B)</span><span class="sxs-lookup"><span data-stu-id="a138a-117">Office 365 Root Certificate Bundle (P7B)</span></span>](http://download.microsoft.com/download/A/5/A/A5AE01F3-D19B-4A11-9407-801263CEF72C/O365_Root_Certs_20170321.p7b) <br/> |<span data-ttu-id="a138a-118">crl.globalsign.net</span><span class="sxs-lookup"><span data-stu-id="a138a-118">crl.globalsign.net</span></span>  <br/> <span data-ttu-id="a138a-119">www.d-trust.net</span><span class="sxs-lookup"><span data-stu-id="a138a-119">www.d-trust.net</span></span>  <br/> |<span data-ttu-id="a138a-120">該当なし</span><span class="sxs-lookup"><span data-stu-id="a138a-120">N/A</span></span>  <br/> |<span data-ttu-id="a138a-121">該当なし</span><span class="sxs-lookup"><span data-stu-id="a138a-121">N/A</span></span>  <br/> |
|[<span data-ttu-id="a138a-122">一般に中間証明書を信頼</span><span class="sxs-lookup"><span data-stu-id="a138a-122">Publicly Trusted Intermediate Certificates</span></span>](https://support.office.com/article/0c03e6b3-e73f-4316-9e2b-bf4091ae96bb#IntermediateCerts) <br/> |[<span data-ttu-id="a138a-123">Office 365 の中間証明書バンドル (P7B)</span><span class="sxs-lookup"><span data-stu-id="a138a-123">Office 365 Intermediate Certificate Bundle (P7B)</span></span>](http://download.microsoft.com/download/4/D/5/4D5339A4-0A4A-46AB-AE52-B179DEDA4BEC/O365_Intermediate_Certs_20170321.p7b)  <br/> |<span data-ttu-id="a138a-124">cdp1.public trust.com</span><span class="sxs-lookup"><span data-stu-id="a138a-124">cdp1.public-trust.com</span></span>  <br/> <span data-ttu-id="a138a-125">crl.cnnic.cn</span><span class="sxs-lookup"><span data-stu-id="a138a-125">crl.cnnic.cn</span></span>  <br/> <span data-ttu-id="a138a-126">crl.entrust.net</span><span class="sxs-lookup"><span data-stu-id="a138a-126">crl.entrust.net</span></span>  <br/> <span data-ttu-id="a138a-127">crl.globalsign.com</span><span class="sxs-lookup"><span data-stu-id="a138a-127">crl.globalsign.com</span></span>  <br/> <span data-ttu-id="a138a-128">crl.globalsign.net</span><span class="sxs-lookup"><span data-stu-id="a138a-128">crl.globalsign.net</span></span>  <br/> <span data-ttu-id="a138a-129">crl.identrust.com</span><span class="sxs-lookup"><span data-stu-id="a138a-129">crl.identrust.com</span></span>  <br/> <span data-ttu-id="a138a-130">crl.thawte.com</span><span class="sxs-lookup"><span data-stu-id="a138a-130">crl.thawte.com</span></span>  <br/> <span data-ttu-id="a138a-131">crl3.digicert.com</span><span class="sxs-lookup"><span data-stu-id="a138a-131">crl3.digicert.com</span></span>  <br/> <span data-ttu-id="a138a-132">crl4.digicert.com</span><span class="sxs-lookup"><span data-stu-id="a138a-132">crl4.digicert.com</span></span>  <br/> <span data-ttu-id="a138a-133">s1.symcb.com</span><span class="sxs-lookup"><span data-stu-id="a138a-133">s1.symcb.com</span></span>  <br/> <span data-ttu-id="a138a-134">www.d-trust.net</span><span class="sxs-lookup"><span data-stu-id="a138a-134">www.d-trust.net</span></span>  <br/> |<span data-ttu-id="a138a-135">isrg.trustid.ocsp.identrust.com</span><span class="sxs-lookup"><span data-stu-id="a138a-135">isrg.trustid.ocsp.identrust.com</span></span>  <br/> <span data-ttu-id="a138a-136">ocsp.digicert.com</span><span class="sxs-lookup"><span data-stu-id="a138a-136">ocsp.digicert.com</span></span>  <br/> <span data-ttu-id="a138a-137">ocsp.entrust.net</span><span class="sxs-lookup"><span data-stu-id="a138a-137">ocsp.entrust.net</span></span>  <br/> <span data-ttu-id="a138a-138">ocsp.globalsign.com</span><span class="sxs-lookup"><span data-stu-id="a138a-138">ocsp.globalsign.com</span></span>  <br/> <span data-ttu-id="a138a-139">ocsp.omniroot.com</span><span class="sxs-lookup"><span data-stu-id="a138a-139">ocsp.omniroot.com</span></span>  <br/> <span data-ttu-id="a138a-140">ocsp.startssl.com</span><span class="sxs-lookup"><span data-stu-id="a138a-140">ocsp.startssl.com</span></span>  <br/> <span data-ttu-id="a138a-141">ocsp.thawte.com</span><span class="sxs-lookup"><span data-stu-id="a138a-141">ocsp.thawte.com</span></span>  <br/> <span data-ttu-id="a138a-142">ocsp2.globalsign.com</span><span class="sxs-lookup"><span data-stu-id="a138a-142">ocsp2.globalsign.com</span></span>  <br/> <span data-ttu-id="a138a-143">ocspcnnicroot.cnnic.cn</span><span class="sxs-lookup"><span data-stu-id="a138a-143">ocspcnnicroot.cnnic.cn</span></span>  <br/> <span data-ttu-id="a138a-144">ルート-c3-ca2-2009.ocsp.d-trust.net</span><span class="sxs-lookup"><span data-stu-id="a138a-144">root-c3-ca2-2009.ocsp.d-trust.net</span></span>  <br/> <span data-ttu-id="a138a-145">root-c3-ca2-ev-2009.ocsp.d-trust.net</span><span class="sxs-lookup"><span data-stu-id="a138a-145">root-c3-ca2-ev-2009.ocsp.d-trust.net</span></span>  <br/> <span data-ttu-id="a138a-146">s2.symcb.com</span><span class="sxs-lookup"><span data-stu-id="a138a-146">s2.symcb.com</span></span>  <br/> |<span data-ttu-id="a138a-147">aia.startssl.com</span><span class="sxs-lookup"><span data-stu-id="a138a-147">aia.startssl.com</span></span>  <br/> <span data-ttu-id="a138a-148">apps.identrust.com</span><span class="sxs-lookup"><span data-stu-id="a138a-148">apps.identrust.com</span></span>  <br/> <span data-ttu-id="a138a-149">cacert.omniroot.com</span><span class="sxs-lookup"><span data-stu-id="a138a-149">cacert.omniroot.com</span></span>  <br/> <span data-ttu-id="a138a-150">www.cnnic.cn</span><span class="sxs-lookup"><span data-stu-id="a138a-150">www.cnnic.cn</span></span>  <br/> |
   
<span data-ttu-id="a138a-151">ルートと証明書プロバイダーに関する追加情報を参照してください次の中間のセクションを展開します。</span><span class="sxs-lookup"><span data-stu-id="a138a-151">Expand the root and intermediate sections below to see additional details about the certificate providers.</span></span>
  
## <a name="office-365-root-certificate-details"></a><span data-ttu-id="a138a-152">Office 365 のルート証明書の詳細</span><span class="sxs-lookup"><span data-stu-id="a138a-152">Office 365 Root Certificate Details</span></span>
<span data-ttu-id="a138a-153"><a name="RootCerts"> </a></span><span class="sxs-lookup"><span data-stu-id="a138a-153"></span></span>

 <span data-ttu-id="a138a-154">**Baltimore CyberTrust Root**</span><span class="sxs-lookup"><span data-stu-id="a138a-154">**Baltimore CyberTrust Root**</span></span>
  
<span data-ttu-id="a138a-155">|:-----|</span><span class="sxs-lookup"><span data-stu-id="a138a-155">|:-----|</span></span>
|<span data-ttu-id="a138a-156">**件名**</span><span class="sxs-lookup"><span data-stu-id="a138a-156">**Subject**</span></span>|
|:-----|
|<span data-ttu-id="a138a-157">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="a138a-157">**Serial Number**</span></span>|
|<span data-ttu-id="a138a-158">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-158"></span></span>|
|<span data-ttu-id="a138a-159">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="a138a-159">**Public Key Length**</span></span>|
|<span data-ttu-id="a138a-160">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-160"></span></span>|
|<span data-ttu-id="a138a-161">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="a138a-161">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a138a-162">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-162"></span></span>|
|<span data-ttu-id="a138a-163">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="a138a-163">**Validity Not Before**</span></span>|
|<span data-ttu-id="a138a-164">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-164"></span></span>|
|<span data-ttu-id="a138a-165">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="a138a-165">**Validity Not After**</span></span>|
|<span data-ttu-id="a138a-166">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-166"></span></span>|
|<span data-ttu-id="a138a-167">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a138a-167">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a138a-168">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-168"></span></span>|
|<span data-ttu-id="a138a-169">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="a138a-169">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a138a-170">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-170"></span></span>|
|<span data-ttu-id="a138a-171">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a138a-171">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a138a-172">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-172"></span></span>|
|<span data-ttu-id="a138a-173">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a138a-173">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a138a-174">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-174"></span></span>|
   
 <span data-ttu-id="a138a-175">**CNNIC のルート**</span><span class="sxs-lookup"><span data-stu-id="a138a-175">**CNNIC ROOT**</span></span>
  
||
|:-----|
|<span data-ttu-id="a138a-176">**件名**</span><span class="sxs-lookup"><span data-stu-id="a138a-176">**Subject**</span></span>|
|<span data-ttu-id="a138a-177">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-177"></span></span>|
|<span data-ttu-id="a138a-178">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="a138a-178">**Serial Number**</span></span>|
|<span data-ttu-id="a138a-179">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-179"></span></span>|
|<span data-ttu-id="a138a-180">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="a138a-180">**Public Key Length**</span></span>|
|<span data-ttu-id="a138a-181">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-181"></span></span>|
|<span data-ttu-id="a138a-182">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="a138a-182">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a138a-183">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-183"></span></span>|
|<span data-ttu-id="a138a-184">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="a138a-184">**Validity Not Before**</span></span>|
|<span data-ttu-id="a138a-185">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-185"></span></span>|
|<span data-ttu-id="a138a-186">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="a138a-186">**Validity Not After**</span></span>|
|<span data-ttu-id="a138a-187">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-187"></span></span>|
|<span data-ttu-id="a138a-188">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a138a-188">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a138a-189">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-189"></span></span>|
|<span data-ttu-id="a138a-190">**機関キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a138a-190">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="a138a-191">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-191"></span></span>|
|<span data-ttu-id="a138a-192">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="a138a-192">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a138a-193">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-193"></span></span>|
|<span data-ttu-id="a138a-194">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a138a-194">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a138a-195">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-195"></span></span>|
|<span data-ttu-id="a138a-196">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a138a-196">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a138a-197">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-197"></span></span>|
   
 <span data-ttu-id="a138a-198">**DigiCert のグローバル ルート CA**</span><span class="sxs-lookup"><span data-stu-id="a138a-198">**DigiCert Global Root CA**</span></span>
  
||
|:-----|
|<span data-ttu-id="a138a-199">**件名**</span><span class="sxs-lookup"><span data-stu-id="a138a-199">**Subject**</span></span>|
|<span data-ttu-id="a138a-200">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-200"></span></span>|
|<span data-ttu-id="a138a-201">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="a138a-201">**Serial Number**</span></span>|
|<span data-ttu-id="a138a-202">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-202"></span></span>|
|<span data-ttu-id="a138a-203">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="a138a-203">**Public Key Length**</span></span>|
|<span data-ttu-id="a138a-204">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-204"></span></span>|
|<span data-ttu-id="a138a-205">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="a138a-205">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a138a-206">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-206"></span></span>|
|<span data-ttu-id="a138a-207">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="a138a-207">**Validity Not Before**</span></span>|
|<span data-ttu-id="a138a-208">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-208"></span></span>|
|<span data-ttu-id="a138a-209">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="a138a-209">**Validity Not After**</span></span>|
|<span data-ttu-id="a138a-210">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-210"></span></span>|
|<span data-ttu-id="a138a-211">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a138a-211">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a138a-212">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-212"></span></span>|
|<span data-ttu-id="a138a-213">**機関キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a138a-213">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="a138a-214">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-214"></span></span>|
|<span data-ttu-id="a138a-215">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="a138a-215">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a138a-216">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-216"></span></span>|
|<span data-ttu-id="a138a-217">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a138a-217">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a138a-218">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-218"></span></span>|
|<span data-ttu-id="a138a-219">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a138a-219">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a138a-220">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-220"></span></span>|
   
 <span data-ttu-id="a138a-221">**DigiCert 高保証 EV のルート CA**</span><span class="sxs-lookup"><span data-stu-id="a138a-221">**DigiCert High Assurance EV Root CA**</span></span>
  
||
|:-----|
|<span data-ttu-id="a138a-222">**件名**</span><span class="sxs-lookup"><span data-stu-id="a138a-222">**Subject**</span></span>|
|<span data-ttu-id="a138a-223">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-223"></span></span>|
|<span data-ttu-id="a138a-224">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="a138a-224">**Serial Number**</span></span>|
|<span data-ttu-id="a138a-225">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-225"></span></span>|
|<span data-ttu-id="a138a-226">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="a138a-226">**Public Key Length**</span></span>|
|<span data-ttu-id="a138a-227">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-227"></span></span>|
|<span data-ttu-id="a138a-228">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="a138a-228">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a138a-229">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-229"></span></span>|
|<span data-ttu-id="a138a-230">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="a138a-230">**Validity Not Before**</span></span>|
|<span data-ttu-id="a138a-231">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-231"></span></span>|
|<span data-ttu-id="a138a-232">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="a138a-232">**Validity Not After**</span></span>|
|<span data-ttu-id="a138a-233">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-233"></span></span>|
|<span data-ttu-id="a138a-234">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a138a-234">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a138a-235">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-235"></span></span>|
|<span data-ttu-id="a138a-236">**機関キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a138a-236">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="a138a-237">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-237"></span></span>|
|<span data-ttu-id="a138a-238">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="a138a-238">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a138a-239">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-239"></span></span>|
|<span data-ttu-id="a138a-240">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a138a-240">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a138a-241">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-241"></span></span>|
|<span data-ttu-id="a138a-242">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a138a-242">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a138a-243">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-243"></span></span>|
   
 <span data-ttu-id="a138a-244">**D 信頼ルート クラス 3 CA 2 2009**</span><span class="sxs-lookup"><span data-stu-id="a138a-244">**D-TRUST Root Class 3 CA 2 2009**</span></span>
  
||
|:-----|
|<span data-ttu-id="a138a-245">**件名**</span><span class="sxs-lookup"><span data-stu-id="a138a-245">**Subject**</span></span>|
|<span data-ttu-id="a138a-246">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-246"></span></span>|
|<span data-ttu-id="a138a-247">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="a138a-247">**Serial Number**</span></span>|
|<span data-ttu-id="a138a-248">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-248"></span></span>|
|<span data-ttu-id="a138a-249">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="a138a-249">**Public Key Length**</span></span>|
|<span data-ttu-id="a138a-250">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-250"></span></span>|
|<span data-ttu-id="a138a-251">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="a138a-251">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a138a-252">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-252"></span></span>|
|<span data-ttu-id="a138a-253">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="a138a-253">**Validity Not Before**</span></span>|
|<span data-ttu-id="a138a-254">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-254"></span></span>|
|<span data-ttu-id="a138a-255">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="a138a-255">**Validity Not After**</span></span>|
|<span data-ttu-id="a138a-256">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-256"></span></span>|
|<span data-ttu-id="a138a-257">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a138a-257">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a138a-258">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-258"></span></span>|
|<span data-ttu-id="a138a-259">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="a138a-259">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a138a-260">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-260"></span></span>|
|<span data-ttu-id="a138a-261">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a138a-261">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a138a-262">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-262"></span></span>|
|<span data-ttu-id="a138a-263">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a138a-263">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a138a-264">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-264"></span></span>|
|<span data-ttu-id="a138a-265">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="a138a-265">**CRL URLs**</span></span>|
|<span data-ttu-id="a138a-266">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-266"></span></span>|
   
 <span data-ttu-id="a138a-267">**クラス 3 の D に信頼できるルート CA 2 EV 2009**</span><span class="sxs-lookup"><span data-stu-id="a138a-267">**D-TRUST Root Class 3 CA 2 EV 2009**</span></span>
  
||
|:-----|
|<span data-ttu-id="a138a-268">**件名**</span><span class="sxs-lookup"><span data-stu-id="a138a-268">**Subject**</span></span>|
|<span data-ttu-id="a138a-269">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-269"></span></span>|
|<span data-ttu-id="a138a-270">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="a138a-270">**Serial Number**</span></span>|
|<span data-ttu-id="a138a-271">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-271"></span></span>|
|<span data-ttu-id="a138a-272">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="a138a-272">**Public Key Length**</span></span>|
|<span data-ttu-id="a138a-273">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-273"></span></span>|
|<span data-ttu-id="a138a-274">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="a138a-274">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a138a-275">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-275"></span></span>|
|<span data-ttu-id="a138a-276">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="a138a-276">**Validity Not Before**</span></span>|
|<span data-ttu-id="a138a-277">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-277"></span></span>|
|<span data-ttu-id="a138a-278">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="a138a-278">**Validity Not After**</span></span>|
|<span data-ttu-id="a138a-279">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-279"></span></span>|
|<span data-ttu-id="a138a-280">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a138a-280">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a138a-281">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-281"></span></span>|
|<span data-ttu-id="a138a-282">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="a138a-282">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a138a-283">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-283"></span></span>|
|<span data-ttu-id="a138a-284">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a138a-284">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a138a-285">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-285"></span></span>|
|<span data-ttu-id="a138a-286">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a138a-286">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a138a-287">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-287"></span></span>|
|<span data-ttu-id="a138a-288">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="a138a-288">**CRL URLs**</span></span>|
|<span data-ttu-id="a138a-289">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-289"></span></span>|
   
 <span data-ttu-id="a138a-290">**DST のルート CA X3**</span><span class="sxs-lookup"><span data-stu-id="a138a-290">**DST Root CA X3**</span></span>
  
||
|:-----|
|<span data-ttu-id="a138a-291">**件名**</span><span class="sxs-lookup"><span data-stu-id="a138a-291">**Subject**</span></span>|
|<span data-ttu-id="a138a-292">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-292"></span></span>|
|<span data-ttu-id="a138a-293">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="a138a-293">**Serial Number**</span></span>|
|<span data-ttu-id="a138a-294">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-294"></span></span>|
|<span data-ttu-id="a138a-295">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="a138a-295">**Public Key Length**</span></span>|
|<span data-ttu-id="a138a-296">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-296"></span></span>|
|<span data-ttu-id="a138a-297">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="a138a-297">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a138a-298">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-298"></span></span>|
|<span data-ttu-id="a138a-299">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="a138a-299">**Validity Not Before**</span></span>|
|<span data-ttu-id="a138a-300">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-300"></span></span>|
|<span data-ttu-id="a138a-301">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="a138a-301">**Validity Not After**</span></span>|
|<span data-ttu-id="a138a-302">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-302"></span></span>|
|<span data-ttu-id="a138a-303">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a138a-303">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a138a-304">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-304"></span></span>|
|<span data-ttu-id="a138a-305">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="a138a-305">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a138a-306">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-306"></span></span>|
|<span data-ttu-id="a138a-307">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a138a-307">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a138a-308">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-308"></span></span>|
|<span data-ttu-id="a138a-309">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a138a-309">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a138a-310">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-310"></span></span>|
   
 <span data-ttu-id="a138a-311">**ルート証明機関の G2 を委託します。**</span><span class="sxs-lookup"><span data-stu-id="a138a-311">**Entrust Root Certification Authority - G2**</span></span>
  
||
|:-----|
|<span data-ttu-id="a138a-312">**件名**</span><span class="sxs-lookup"><span data-stu-id="a138a-312">**Subject**</span></span>|
|<span data-ttu-id="a138a-313">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-313"></span></span>|
|<span data-ttu-id="a138a-314">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="a138a-314">**Serial Number**</span></span>|
|<span data-ttu-id="a138a-315">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-315"></span></span>|
|<span data-ttu-id="a138a-316">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="a138a-316">**Public Key Length**</span></span>|
|<span data-ttu-id="a138a-317">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-317"></span></span>|
|<span data-ttu-id="a138a-318">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="a138a-318">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a138a-319">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-319"></span></span>|
|<span data-ttu-id="a138a-320">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="a138a-320">**Validity Not Before**</span></span>|
|<span data-ttu-id="a138a-321">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-321"></span></span>|
|<span data-ttu-id="a138a-322">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="a138a-322">**Validity Not After**</span></span>|
|<span data-ttu-id="a138a-323">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-323"></span></span>|
|<span data-ttu-id="a138a-324">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a138a-324">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a138a-325">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-325"></span></span>|
|<span data-ttu-id="a138a-326">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="a138a-326">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a138a-327">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-327"></span></span>|
|<span data-ttu-id="a138a-328">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a138a-328">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a138a-329">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-329"></span></span>|
|<span data-ttu-id="a138a-330">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a138a-330">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a138a-331">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-331"></span></span>|
   
 <span data-ttu-id="a138a-332">**Entrust.net Certification Authority (2048)**</span><span class="sxs-lookup"><span data-stu-id="a138a-332">**Entrust.net Certification Authority (2048)**</span></span>
  
||
|:-----|
|<span data-ttu-id="a138a-333">**件名**</span><span class="sxs-lookup"><span data-stu-id="a138a-333">**Subject**</span></span>|
|<span data-ttu-id="a138a-334">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-334"></span></span>|
|<span data-ttu-id="a138a-335">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="a138a-335">**Serial Number**</span></span>|
|<span data-ttu-id="a138a-336">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-336"></span></span>|
|<span data-ttu-id="a138a-337">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="a138a-337">**Public Key Length**</span></span>|
|<span data-ttu-id="a138a-338">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-338"></span></span>|
|<span data-ttu-id="a138a-339">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="a138a-339">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a138a-340">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-340"></span></span>|
|<span data-ttu-id="a138a-341">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="a138a-341">**Validity Not Before**</span></span>|
|<span data-ttu-id="a138a-342">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-342"></span></span>|
|<span data-ttu-id="a138a-343">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="a138a-343">**Validity Not After**</span></span>|
|<span data-ttu-id="a138a-344">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-344"></span></span>|
|<span data-ttu-id="a138a-345">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a138a-345">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a138a-346">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-346"></span></span>|
|<span data-ttu-id="a138a-347">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="a138a-347">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a138a-348">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-348"></span></span>|
|<span data-ttu-id="a138a-349">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a138a-349">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a138a-350">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-350"></span></span>|
|<span data-ttu-id="a138a-351">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a138a-351">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a138a-352">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-352"></span></span>|
   
 <span data-ttu-id="a138a-353">**GlobalSign**</span><span class="sxs-lookup"><span data-stu-id="a138a-353">**GlobalSign**</span></span>
  
||
|:-----|
|<span data-ttu-id="a138a-354">**件名**</span><span class="sxs-lookup"><span data-stu-id="a138a-354">**Subject**</span></span>|
|<span data-ttu-id="a138a-355">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-355"></span></span>|
|<span data-ttu-id="a138a-356">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="a138a-356">**Serial Number**</span></span>|
|<span data-ttu-id="a138a-357">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-357"></span></span>|
|<span data-ttu-id="a138a-358">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="a138a-358">**Public Key Length**</span></span>|
|<span data-ttu-id="a138a-359">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-359"></span></span>|
|<span data-ttu-id="a138a-360">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="a138a-360">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a138a-361">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-361"></span></span>|
|<span data-ttu-id="a138a-362">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="a138a-362">**Validity Not Before**</span></span>|
|<span data-ttu-id="a138a-363">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-363"></span></span>|
|<span data-ttu-id="a138a-364">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="a138a-364">**Validity Not After**</span></span>|
|<span data-ttu-id="a138a-365">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-365"></span></span>|
|<span data-ttu-id="a138a-366">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a138a-366">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a138a-367">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-367"></span></span>|
|<span data-ttu-id="a138a-368">**機関キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a138a-368">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="a138a-369">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-369"></span></span>|
|<span data-ttu-id="a138a-370">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="a138a-370">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a138a-371">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-371"></span></span>|
|<span data-ttu-id="a138a-372">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a138a-372">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a138a-373">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-373"></span></span>|
|<span data-ttu-id="a138a-374">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a138a-374">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a138a-375">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-375"></span></span>|
|<span data-ttu-id="a138a-376">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="a138a-376">**CRL URLs**</span></span>|
|<span data-ttu-id="a138a-377">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-377"></span></span>|
   
 <span data-ttu-id="a138a-378">**GlobalSign Root CA**</span><span class="sxs-lookup"><span data-stu-id="a138a-378">**GlobalSign Root CA**</span></span>
  
||
|:-----|
|<span data-ttu-id="a138a-379">**件名**</span><span class="sxs-lookup"><span data-stu-id="a138a-379">**Subject**</span></span>|
|<span data-ttu-id="a138a-380">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-380"></span></span>|
|<span data-ttu-id="a138a-381">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="a138a-381">**Serial Number**</span></span>|
|<span data-ttu-id="a138a-382">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-382"></span></span>|
|<span data-ttu-id="a138a-383">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="a138a-383">**Public Key Length**</span></span>|
|<span data-ttu-id="a138a-384">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-384"></span></span>|
|<span data-ttu-id="a138a-385">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="a138a-385">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a138a-386">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-386"></span></span>|
|<span data-ttu-id="a138a-387">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="a138a-387">**Validity Not Before**</span></span>|
|<span data-ttu-id="a138a-388">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-388"></span></span>|
|<span data-ttu-id="a138a-389">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="a138a-389">**Validity Not After**</span></span>|
|<span data-ttu-id="a138a-390">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-390"></span></span>|
|<span data-ttu-id="a138a-391">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a138a-391">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a138a-392">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-392"></span></span>|
|<span data-ttu-id="a138a-393">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="a138a-393">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a138a-394">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-394"></span></span>|
|<span data-ttu-id="a138a-395">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a138a-395">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a138a-396">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-396"></span></span>|
|<span data-ttu-id="a138a-397">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a138a-397">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a138a-398">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-398"></span></span>|
   
 <span data-ttu-id="a138a-399">**thawte プライマリ ルート CA の場合は、G3**</span><span class="sxs-lookup"><span data-stu-id="a138a-399">**thawte Primary Root CA - G3**</span></span>
  
||
|:-----|
|<span data-ttu-id="a138a-400">**件名**</span><span class="sxs-lookup"><span data-stu-id="a138a-400">**Subject**</span></span>|
|<span data-ttu-id="a138a-401">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-401"></span></span>|
|<span data-ttu-id="a138a-402">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="a138a-402">**Serial Number**</span></span>|
|<span data-ttu-id="a138a-403">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-403"></span></span>|
|<span data-ttu-id="a138a-404">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="a138a-404">**Public Key Length**</span></span>|
|<span data-ttu-id="a138a-405">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-405"></span></span>|
|<span data-ttu-id="a138a-406">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="a138a-406">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a138a-407">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-407"></span></span>|
|<span data-ttu-id="a138a-408">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="a138a-408">**Validity Not Before**</span></span>|
|<span data-ttu-id="a138a-409">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-409"></span></span>|
|<span data-ttu-id="a138a-410">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="a138a-410">**Validity Not After**</span></span>|
|<span data-ttu-id="a138a-411">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-411"></span></span>|
|<span data-ttu-id="a138a-412">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a138a-412">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a138a-413">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-413"></span></span>|
|<span data-ttu-id="a138a-414">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="a138a-414">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a138a-415">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-415"></span></span>|
|<span data-ttu-id="a138a-416">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a138a-416">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a138a-417">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-417"></span></span>|
|<span data-ttu-id="a138a-418">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a138a-418">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a138a-419">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-419"></span></span>|
   
 <span data-ttu-id="a138a-420">**VeriSign クラス 3 の主な公共の証明機関の G5**</span><span class="sxs-lookup"><span data-stu-id="a138a-420">**VeriSign Class 3 Public Primary Certification Authority - G5**</span></span>
  
||
|:-----|
|<span data-ttu-id="a138a-421">**件名**</span><span class="sxs-lookup"><span data-stu-id="a138a-421">**Subject**</span></span>|
|<span data-ttu-id="a138a-422">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-422"></span></span>|
|<span data-ttu-id="a138a-423">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="a138a-423">**Serial Number**</span></span>|
|<span data-ttu-id="a138a-424">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-424"></span></span>|
|<span data-ttu-id="a138a-425">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="a138a-425">**Public Key Length**</span></span>|
|<span data-ttu-id="a138a-426">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-426"></span></span>|
|<span data-ttu-id="a138a-427">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="a138a-427">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a138a-428">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-428"></span></span>|
|<span data-ttu-id="a138a-429">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="a138a-429">**Validity Not Before**</span></span>|
|<span data-ttu-id="a138a-430">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-430"></span></span>|
|<span data-ttu-id="a138a-431">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="a138a-431">**Validity Not After**</span></span>|
|<span data-ttu-id="a138a-432">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-432"></span></span>|
|<span data-ttu-id="a138a-433">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a138a-433">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a138a-434">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-434"></span></span>|
|<span data-ttu-id="a138a-435">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="a138a-435">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a138a-436">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-436"></span></span>|
|<span data-ttu-id="a138a-437">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a138a-437">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a138a-438">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-438"></span></span>|
|<span data-ttu-id="a138a-439">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a138a-439">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a138a-440">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-440"></span></span>|
   
## <a name="office-365-intermediate-certificate-details"></a><span data-ttu-id="a138a-441">Office 365 の中間の証明書の詳細</span><span class="sxs-lookup"><span data-stu-id="a138a-441">Office 365 Intermediate Certificate Details</span></span>
<span data-ttu-id="a138a-442"><a name="IntermediateCerts"> </a></span><span class="sxs-lookup"><span data-stu-id="a138a-442"></span></span>

 <span data-ttu-id="a138a-443">**CNNIC SHA256 SSL**</span><span class="sxs-lookup"><span data-stu-id="a138a-443">**CNNIC SHA256 SSL**</span></span>
  
||
|:-----|
|<span data-ttu-id="a138a-444">**件名**</span><span class="sxs-lookup"><span data-stu-id="a138a-444">**Subject**</span></span>|
|<span data-ttu-id="a138a-445">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-445"></span></span>|
|<span data-ttu-id="a138a-446">**発行者**</span><span class="sxs-lookup"><span data-stu-id="a138a-446">**Issuer**</span></span>|
|<span data-ttu-id="a138a-447">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-447"></span></span>|
|<span data-ttu-id="a138a-448">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="a138a-448">**Serial Number**</span></span>|
|<span data-ttu-id="a138a-449">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-449"></span></span>|
|<span data-ttu-id="a138a-450">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="a138a-450">**Public Key Length**</span></span>|
|<span data-ttu-id="a138a-451">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-451"></span></span>|
|<span data-ttu-id="a138a-452">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="a138a-452">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a138a-453">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-453"></span></span>|
|<span data-ttu-id="a138a-454">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="a138a-454">**Validity Not Before**</span></span>|
|<span data-ttu-id="a138a-455">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-455"></span></span>|
|<span data-ttu-id="a138a-456">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="a138a-456">**Validity Not After**</span></span>|
|<span data-ttu-id="a138a-457">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-457"></span></span>|
|<span data-ttu-id="a138a-458">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a138a-458">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a138a-459">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-459"></span></span>|
|<span data-ttu-id="a138a-460">**機関キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a138a-460">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="a138a-461">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-461"></span></span>|
|<span data-ttu-id="a138a-462">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="a138a-462">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a138a-463">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-463"></span></span>|
|<span data-ttu-id="a138a-464">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a138a-464">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a138a-465">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-465"></span></span>|
|<span data-ttu-id="a138a-466">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a138a-466">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a138a-467">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-467"></span></span>|
|<span data-ttu-id="a138a-468">**AIA の Url**</span><span class="sxs-lookup"><span data-stu-id="a138a-468">**AIA URLs**</span></span>|
|<span data-ttu-id="a138a-469">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-469"></span></span>|
|<span data-ttu-id="a138a-470">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="a138a-470">**CRL URLs**</span></span>|
|<span data-ttu-id="a138a-471">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-471"></span></span>|
|<span data-ttu-id="a138a-472">**OCSP の Url**</span><span class="sxs-lookup"><span data-stu-id="a138a-472">**OCSP URLs**</span></span>|
|<span data-ttu-id="a138a-473">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-473"></span></span>|
   
 <span data-ttu-id="a138a-474">**D 信頼 SSL クラス 3 CA 1 2009**</span><span class="sxs-lookup"><span data-stu-id="a138a-474">**D-TRUST SSL Class 3 CA 1 2009**</span></span>
  
||
|:-----|
|<span data-ttu-id="a138a-475">**件名**</span><span class="sxs-lookup"><span data-stu-id="a138a-475">**Subject**</span></span>|
|<span data-ttu-id="a138a-476">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-476"></span></span>|
|<span data-ttu-id="a138a-477">**発行者**</span><span class="sxs-lookup"><span data-stu-id="a138a-477">**Issuer**</span></span>|
|<span data-ttu-id="a138a-478">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-478"></span></span>|
|<span data-ttu-id="a138a-479">**代わりのサブジェクト名**</span><span class="sxs-lookup"><span data-stu-id="a138a-479">**Subject Alternative Name**</span></span>|
|<span data-ttu-id="a138a-480">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-480"></span></span>|
|<span data-ttu-id="a138a-481">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="a138a-481">**Serial Number**</span></span>|
|<span data-ttu-id="a138a-482">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-482"></span></span>|
|<span data-ttu-id="a138a-483">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="a138a-483">**Public Key Length**</span></span>|
|<span data-ttu-id="a138a-484">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-484"></span></span>|
|<span data-ttu-id="a138a-485">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="a138a-485">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a138a-486">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-486"></span></span>|
|<span data-ttu-id="a138a-487">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="a138a-487">**Validity Not Before**</span></span>|
|<span data-ttu-id="a138a-488">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-488"></span></span>|
|<span data-ttu-id="a138a-489">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="a138a-489">**Validity Not After**</span></span>|
|<span data-ttu-id="a138a-490">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-490"></span></span>|
|<span data-ttu-id="a138a-491">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a138a-491">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a138a-492">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-492"></span></span>|
|<span data-ttu-id="a138a-493">**機関キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a138a-493">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="a138a-494">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-494"></span></span>|
|<span data-ttu-id="a138a-495">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="a138a-495">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a138a-496">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-496"></span></span>|
|<span data-ttu-id="a138a-497">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a138a-497">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a138a-498">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-498"></span></span>|
|<span data-ttu-id="a138a-499">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a138a-499">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a138a-500">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-500"></span></span>|
|<span data-ttu-id="a138a-501">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="a138a-501">**CRL URLs**</span></span>|
|<span data-ttu-id="a138a-502">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-502"></span></span>|
|<span data-ttu-id="a138a-503">**OCSP の Url**</span><span class="sxs-lookup"><span data-stu-id="a138a-503">**OCSP URLs**</span></span>|
|<span data-ttu-id="a138a-504">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-504"></span></span>|
   
 <span data-ttu-id="a138a-505">**D 信頼 SSL クラス 3 CA 1 EV 2009**</span><span class="sxs-lookup"><span data-stu-id="a138a-505">**D-TRUST SSL Class 3 CA 1 EV 2009**</span></span>
  
||
|:-----|
|<span data-ttu-id="a138a-506">**件名**</span><span class="sxs-lookup"><span data-stu-id="a138a-506">**Subject**</span></span>|
|<span data-ttu-id="a138a-507">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-507"></span></span>|
|<span data-ttu-id="a138a-508">**発行者**</span><span class="sxs-lookup"><span data-stu-id="a138a-508">**Issuer**</span></span>|
|<span data-ttu-id="a138a-509">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-509"></span></span>|
|<span data-ttu-id="a138a-510">**代わりのサブジェクト名**</span><span class="sxs-lookup"><span data-stu-id="a138a-510">**Subject Alternative Name**</span></span>|
|<span data-ttu-id="a138a-511">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-511"></span></span>|
|<span data-ttu-id="a138a-512">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="a138a-512">**Serial Number**</span></span>|
|<span data-ttu-id="a138a-513">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-513"></span></span>|
|<span data-ttu-id="a138a-514">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="a138a-514">**Public Key Length**</span></span>|
|<span data-ttu-id="a138a-515">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-515"></span></span>|
|<span data-ttu-id="a138a-516">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="a138a-516">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a138a-517">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-517"></span></span>|
|<span data-ttu-id="a138a-518">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="a138a-518">**Validity Not Before**</span></span>|
|<span data-ttu-id="a138a-519">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-519"></span></span>|
|<span data-ttu-id="a138a-520">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="a138a-520">**Validity Not After**</span></span>|
|<span data-ttu-id="a138a-521">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-521"></span></span>|
|<span data-ttu-id="a138a-522">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a138a-522">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a138a-523">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-523"></span></span>|
|<span data-ttu-id="a138a-524">**機関キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a138a-524">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="a138a-525">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-525"></span></span>|
|<span data-ttu-id="a138a-526">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="a138a-526">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a138a-527">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-527"></span></span>|
|<span data-ttu-id="a138a-528">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a138a-528">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a138a-529">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-529"></span></span>|
|<span data-ttu-id="a138a-530">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a138a-530">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a138a-531">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-531"></span></span>|
|<span data-ttu-id="a138a-532">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="a138a-532">**CRL URLs**</span></span>|
|<span data-ttu-id="a138a-533">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-533"></span></span>|
|<span data-ttu-id="a138a-534">**OCSP の Url**</span><span class="sxs-lookup"><span data-stu-id="a138a-534">**OCSP URLs**</span></span>|
|<span data-ttu-id="a138a-535">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-535"></span></span>|
   
 <span data-ttu-id="a138a-536">**DigiCert のクラウド サービスの CA 1**</span><span class="sxs-lookup"><span data-stu-id="a138a-536">**DigiCert Cloud Services CA-1**</span></span>
  
||
|:-----|
|<span data-ttu-id="a138a-537">**件名**</span><span class="sxs-lookup"><span data-stu-id="a138a-537">**Subject**</span></span>|
|<span data-ttu-id="a138a-538">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-538"></span></span>|
|<span data-ttu-id="a138a-539">**発行者**</span><span class="sxs-lookup"><span data-stu-id="a138a-539">**Issuer**</span></span>|
|<span data-ttu-id="a138a-540">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-540"></span></span>|
|<span data-ttu-id="a138a-541">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="a138a-541">**Serial Number**</span></span>|
|<span data-ttu-id="a138a-542">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-542"></span></span>|
|<span data-ttu-id="a138a-543">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="a138a-543">**Public Key Length**</span></span>|
|<span data-ttu-id="a138a-544">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-544"></span></span>|
|<span data-ttu-id="a138a-545">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="a138a-545">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a138a-546">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-546"></span></span>|
|<span data-ttu-id="a138a-547">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="a138a-547">**Validity Not Before**</span></span>|
|<span data-ttu-id="a138a-548">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-548"></span></span>|
|<span data-ttu-id="a138a-549">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="a138a-549">**Validity Not After**</span></span>|
|<span data-ttu-id="a138a-550">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-550"></span></span>|
|<span data-ttu-id="a138a-551">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a138a-551">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a138a-552">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-552"></span></span>|
|<span data-ttu-id="a138a-553">**機関キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a138a-553">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="a138a-554">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-554"></span></span>|
|<span data-ttu-id="a138a-555">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="a138a-555">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a138a-556">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-556"></span></span>|
|<span data-ttu-id="a138a-557">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a138a-557">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a138a-558">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-558"></span></span>|
|<span data-ttu-id="a138a-559">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a138a-559">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a138a-560">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-560"></span></span>|
|<span data-ttu-id="a138a-561">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="a138a-561">**CRL URLs**</span></span>|
|<span data-ttu-id="a138a-562">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-562"></span></span>|
|<span data-ttu-id="a138a-563">**OCSP の Url**</span><span class="sxs-lookup"><span data-stu-id="a138a-563">**OCSP URLs**</span></span>|
|<span data-ttu-id="a138a-564">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-564"></span></span>|
   
 <span data-ttu-id="a138a-565">**DigiCert SHA2 高保証サーバー CA**</span><span class="sxs-lookup"><span data-stu-id="a138a-565">**DigiCert SHA2 High Assurance Server CA**</span></span>
  
||
|:-----|
|<span data-ttu-id="a138a-566">**件名**</span><span class="sxs-lookup"><span data-stu-id="a138a-566">**Subject**</span></span>|
|<span data-ttu-id="a138a-567">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-567"></span></span>|
|<span data-ttu-id="a138a-568">**発行者**</span><span class="sxs-lookup"><span data-stu-id="a138a-568">**Issuer**</span></span>|
|<span data-ttu-id="a138a-569">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-569"></span></span>|
|<span data-ttu-id="a138a-570">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="a138a-570">**Serial Number**</span></span>|
|<span data-ttu-id="a138a-571">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-571"></span></span>|
|<span data-ttu-id="a138a-572">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="a138a-572">**Public Key Length**</span></span>|
|<span data-ttu-id="a138a-573">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-573"></span></span>|
|<span data-ttu-id="a138a-574">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="a138a-574">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a138a-575">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-575"></span></span>|
|<span data-ttu-id="a138a-576">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="a138a-576">**Validity Not Before**</span></span>|
|<span data-ttu-id="a138a-577">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-577"></span></span>|
|<span data-ttu-id="a138a-578">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="a138a-578">**Validity Not After**</span></span>|
|<span data-ttu-id="a138a-579">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-579"></span></span>|
|<span data-ttu-id="a138a-580">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a138a-580">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a138a-581">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-581"></span></span>|
|<span data-ttu-id="a138a-582">**機関キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a138a-582">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="a138a-583">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-583"></span></span>|
|<span data-ttu-id="a138a-584">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="a138a-584">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a138a-585">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-585"></span></span>|
|<span data-ttu-id="a138a-586">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a138a-586">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a138a-587">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-587"></span></span>|
|<span data-ttu-id="a138a-588">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a138a-588">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a138a-589">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-589"></span></span>|
|<span data-ttu-id="a138a-590">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="a138a-590">**CRL URLs**</span></span>|
|<span data-ttu-id="a138a-591">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-591"></span></span>|
|<span data-ttu-id="a138a-592">**OCSP の Url**</span><span class="sxs-lookup"><span data-stu-id="a138a-592">**OCSP URLs**</span></span>|
|<span data-ttu-id="a138a-593">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-593"></span></span>|
   
 <span data-ttu-id="a138a-594">**DigiCert SHA2 セキュリティで保護されたサーバーの CA**</span><span class="sxs-lookup"><span data-stu-id="a138a-594">**DigiCert SHA2 Secure Server CA**</span></span>
  
||
|:-----|
|<span data-ttu-id="a138a-595">**件名**</span><span class="sxs-lookup"><span data-stu-id="a138a-595">**Subject**</span></span>|
|<span data-ttu-id="a138a-596">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-596"></span></span>|
|<span data-ttu-id="a138a-597">**発行者**</span><span class="sxs-lookup"><span data-stu-id="a138a-597">**Issuer**</span></span>|
|<span data-ttu-id="a138a-598">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-598"></span></span>|
|<span data-ttu-id="a138a-599">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="a138a-599">**Serial Number**</span></span>|
|<span data-ttu-id="a138a-600">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-600"></span></span>|
|<span data-ttu-id="a138a-601">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="a138a-601">**Public Key Length**</span></span>|
|<span data-ttu-id="a138a-602">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-602"></span></span>|
|<span data-ttu-id="a138a-603">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="a138a-603">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a138a-604">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-604"></span></span>|
|<span data-ttu-id="a138a-605">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="a138a-605">**Validity Not Before**</span></span>|
|<span data-ttu-id="a138a-606">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-606"></span></span>|
|<span data-ttu-id="a138a-607">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="a138a-607">**Validity Not After**</span></span>|
|<span data-ttu-id="a138a-608">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-608"></span></span>|
|<span data-ttu-id="a138a-609">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a138a-609">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a138a-610">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-610"></span></span>|
|<span data-ttu-id="a138a-611">**機関キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a138a-611">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="a138a-612">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-612"></span></span>|
|<span data-ttu-id="a138a-613">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="a138a-613">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a138a-614">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-614"></span></span>|
|<span data-ttu-id="a138a-615">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a138a-615">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a138a-616">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-616"></span></span>|
|<span data-ttu-id="a138a-617">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a138a-617">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a138a-618">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-618"></span></span>|
|<span data-ttu-id="a138a-619">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="a138a-619">**CRL URLs**</span></span>|
|<span data-ttu-id="a138a-620">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-620"></span></span>|
|<span data-ttu-id="a138a-621">**OCSP の Url**</span><span class="sxs-lookup"><span data-stu-id="a138a-621">**OCSP URLs**</span></span>|
|<span data-ttu-id="a138a-622">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-622"></span></span>|
   
 <span data-ttu-id="a138a-623">**証明機関 - L1C を委託します。**</span><span class="sxs-lookup"><span data-stu-id="a138a-623">**Entrust Certification Authority - L1C**</span></span>
  
||
|:-----|
|<span data-ttu-id="a138a-624">**件名**</span><span class="sxs-lookup"><span data-stu-id="a138a-624">**Subject**</span></span>|
|<span data-ttu-id="a138a-625">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-625"></span></span>|
|<span data-ttu-id="a138a-626">**発行者**</span><span class="sxs-lookup"><span data-stu-id="a138a-626">**Issuer**</span></span>|
|<span data-ttu-id="a138a-627">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-627"></span></span>|
|<span data-ttu-id="a138a-628">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="a138a-628">**Serial Number**</span></span>|
|<span data-ttu-id="a138a-629">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-629"></span></span>|
|<span data-ttu-id="a138a-630">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="a138a-630">**Public Key Length**</span></span>|
|<span data-ttu-id="a138a-631">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-631"></span></span>|
|<span data-ttu-id="a138a-632">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="a138a-632">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a138a-633">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-633"></span></span>|
|<span data-ttu-id="a138a-634">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="a138a-634">**Validity Not Before**</span></span>|
|<span data-ttu-id="a138a-635">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-635"></span></span>|
|<span data-ttu-id="a138a-636">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="a138a-636">**Validity Not After**</span></span>|
|<span data-ttu-id="a138a-637">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-637"></span></span>|
|<span data-ttu-id="a138a-638">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a138a-638">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a138a-639">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-639"></span></span>|
|<span data-ttu-id="a138a-640">**機関キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a138a-640">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="a138a-641">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-641"></span></span>|
|<span data-ttu-id="a138a-642">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="a138a-642">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a138a-643">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-643"></span></span>|
|<span data-ttu-id="a138a-644">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a138a-644">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a138a-645">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-645"></span></span>|
|<span data-ttu-id="a138a-646">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a138a-646">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a138a-647">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-647"></span></span>|
|<span data-ttu-id="a138a-648">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="a138a-648">**CRL URLs**</span></span>|
|<span data-ttu-id="a138a-649">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-649"></span></span>|
|<span data-ttu-id="a138a-650">**OCSP の Url**</span><span class="sxs-lookup"><span data-stu-id="a138a-650">**OCSP URLs**</span></span>|
|<span data-ttu-id="a138a-651">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-651"></span></span>|
   
 <span data-ttu-id="a138a-652">**証明機関 - L1K を委託します。**</span><span class="sxs-lookup"><span data-stu-id="a138a-652">**Entrust Certification Authority - L1K**</span></span>
  
||
|:-----|
|<span data-ttu-id="a138a-653">**件名**</span><span class="sxs-lookup"><span data-stu-id="a138a-653">**Subject**</span></span>|
|<span data-ttu-id="a138a-654">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-654"></span></span>|
|<span data-ttu-id="a138a-655">**発行者**</span><span class="sxs-lookup"><span data-stu-id="a138a-655">**Issuer**</span></span>|
|<span data-ttu-id="a138a-656">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-656"></span></span>|
|<span data-ttu-id="a138a-657">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="a138a-657">**Serial Number**</span></span>|
|<span data-ttu-id="a138a-658">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-658"></span></span>|
|<span data-ttu-id="a138a-659">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="a138a-659">**Public Key Length**</span></span>|
|<span data-ttu-id="a138a-660">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-660"></span></span>|
|<span data-ttu-id="a138a-661">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="a138a-661">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a138a-662">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-662"></span></span>|
|<span data-ttu-id="a138a-663">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="a138a-663">**Validity Not Before**</span></span>|
|<span data-ttu-id="a138a-664">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-664"></span></span>|
|<span data-ttu-id="a138a-665">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="a138a-665">**Validity Not After**</span></span>|
|<span data-ttu-id="a138a-666">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-666"></span></span>|
|<span data-ttu-id="a138a-667">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a138a-667">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a138a-668">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-668"></span></span>|
|<span data-ttu-id="a138a-669">**機関キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a138a-669">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="a138a-670">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-670"></span></span>|
|<span data-ttu-id="a138a-671">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="a138a-671">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a138a-672">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-672"></span></span>|
|<span data-ttu-id="a138a-673">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a138a-673">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a138a-674">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-674"></span></span>|
|<span data-ttu-id="a138a-675">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a138a-675">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a138a-676">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-676"></span></span>|
|<span data-ttu-id="a138a-677">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="a138a-677">**CRL URLs**</span></span>|
|<span data-ttu-id="a138a-678">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-678"></span></span>|
|<span data-ttu-id="a138a-679">**OCSP の Url**</span><span class="sxs-lookup"><span data-stu-id="a138a-679">**OCSP URLs**</span></span>|
|<span data-ttu-id="a138a-680">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-680"></span></span>|
   
 <span data-ttu-id="a138a-681">**GlobalSign**</span><span class="sxs-lookup"><span data-stu-id="a138a-681">**GlobalSign**</span></span>
  
||
|:-----|
|<span data-ttu-id="a138a-682">**件名**</span><span class="sxs-lookup"><span data-stu-id="a138a-682">**Subject**</span></span>|
|<span data-ttu-id="a138a-683">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-683"></span></span>|
|<span data-ttu-id="a138a-684">**発行者**</span><span class="sxs-lookup"><span data-stu-id="a138a-684">**Issuer**</span></span>|
|<span data-ttu-id="a138a-685">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-685"></span></span>|
|<span data-ttu-id="a138a-686">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="a138a-686">**Serial Number**</span></span>|
|<span data-ttu-id="a138a-687">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-687"></span></span>|
|<span data-ttu-id="a138a-688">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="a138a-688">**Public Key Length**</span></span>|
|<span data-ttu-id="a138a-689">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-689"></span></span>|
|<span data-ttu-id="a138a-690">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="a138a-690">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a138a-691">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-691"></span></span>|
|<span data-ttu-id="a138a-692">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="a138a-692">**Validity Not Before**</span></span>|
|<span data-ttu-id="a138a-693">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-693"></span></span>|
|<span data-ttu-id="a138a-694">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="a138a-694">**Validity Not After**</span></span>|
|<span data-ttu-id="a138a-695">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-695"></span></span>|
|<span data-ttu-id="a138a-696">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a138a-696">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a138a-697">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-697"></span></span>|
|<span data-ttu-id="a138a-698">**機関キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a138a-698">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="a138a-699">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-699"></span></span>|
|<span data-ttu-id="a138a-700">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="a138a-700">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a138a-701">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-701"></span></span>|
|<span data-ttu-id="a138a-702">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a138a-702">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a138a-703">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-703"></span></span>|
|<span data-ttu-id="a138a-704">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a138a-704">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a138a-705">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-705"></span></span>|
|<span data-ttu-id="a138a-706">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="a138a-706">**CRL URLs**</span></span>|
|<span data-ttu-id="a138a-707">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-707"></span></span>|
|<span data-ttu-id="a138a-708">**OCSP の Url**</span><span class="sxs-lookup"><span data-stu-id="a138a-708">**OCSP URLs**</span></span>|
|<span data-ttu-id="a138a-709">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-709"></span></span>|
   
 <span data-ttu-id="a138a-710">**GlobalSign の CA の SHA256 の G2 の検証の拡張**</span><span class="sxs-lookup"><span data-stu-id="a138a-710">**GlobalSign Extended Validation CA - SHA256 - G2**</span></span>
  
||
|:-----|
|<span data-ttu-id="a138a-711">**件名**</span><span class="sxs-lookup"><span data-stu-id="a138a-711">**Subject**</span></span>|
|<span data-ttu-id="a138a-712">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-712"></span></span>|
|<span data-ttu-id="a138a-713">**発行者**</span><span class="sxs-lookup"><span data-stu-id="a138a-713">**Issuer**</span></span>|
|<span data-ttu-id="a138a-714">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-714"></span></span>|
|<span data-ttu-id="a138a-715">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="a138a-715">**Serial Number**</span></span>|
|<span data-ttu-id="a138a-716">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-716"></span></span>|
|<span data-ttu-id="a138a-717">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="a138a-717">**Public Key Length**</span></span>|
|<span data-ttu-id="a138a-718">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-718"></span></span>|
|<span data-ttu-id="a138a-719">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="a138a-719">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a138a-720">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-720"></span></span>|
|<span data-ttu-id="a138a-721">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="a138a-721">**Validity Not Before**</span></span>|
|<span data-ttu-id="a138a-722">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-722"></span></span>|
|<span data-ttu-id="a138a-723">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="a138a-723">**Validity Not After**</span></span>|
|<span data-ttu-id="a138a-724">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-724"></span></span>|
|<span data-ttu-id="a138a-725">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a138a-725">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a138a-726">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-726"></span></span>|
|<span data-ttu-id="a138a-727">**機関キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a138a-727">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="a138a-728">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-728"></span></span>|
|<span data-ttu-id="a138a-729">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="a138a-729">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a138a-730">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-730"></span></span>|
|<span data-ttu-id="a138a-731">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a138a-731">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a138a-732">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-732"></span></span>|
|<span data-ttu-id="a138a-733">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a138a-733">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a138a-734">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-734"></span></span>|
|<span data-ttu-id="a138a-735">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="a138a-735">**CRL URLs**</span></span>|
|<span data-ttu-id="a138a-736">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-736"></span></span>|
|<span data-ttu-id="a138a-737">**OCSP の Url**</span><span class="sxs-lookup"><span data-stu-id="a138a-737">**OCSP URLs**</span></span>|
|<span data-ttu-id="a138a-738">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-738"></span></span>|
   
 <span data-ttu-id="a138a-739">**GlobalSign の CA の SHA256 の G3 の検証の拡張**</span><span class="sxs-lookup"><span data-stu-id="a138a-739">**GlobalSign Extended Validation CA - SHA256 - G3**</span></span>
  
||
|:-----|
|<span data-ttu-id="a138a-740">**件名**</span><span class="sxs-lookup"><span data-stu-id="a138a-740">**Subject**</span></span>|
|<span data-ttu-id="a138a-741">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-741"></span></span>|
|<span data-ttu-id="a138a-742">**発行者**</span><span class="sxs-lookup"><span data-stu-id="a138a-742">**Issuer**</span></span>|
|<span data-ttu-id="a138a-743">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-743"></span></span>|
|<span data-ttu-id="a138a-744">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="a138a-744">**Serial Number**</span></span>|
|<span data-ttu-id="a138a-745">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-745"></span></span>|
|<span data-ttu-id="a138a-746">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="a138a-746">**Public Key Length**</span></span>|
|<span data-ttu-id="a138a-747">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-747"></span></span>|
|<span data-ttu-id="a138a-748">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="a138a-748">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a138a-749">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-749"></span></span>|
|<span data-ttu-id="a138a-750">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="a138a-750">**Validity Not Before**</span></span>|
|<span data-ttu-id="a138a-751">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-751"></span></span>|
|<span data-ttu-id="a138a-752">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="a138a-752">**Validity Not After**</span></span>|
|<span data-ttu-id="a138a-753">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-753"></span></span>|
|<span data-ttu-id="a138a-754">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a138a-754">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a138a-755">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-755"></span></span>|
|<span data-ttu-id="a138a-756">**機関キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a138a-756">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="a138a-757">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-757"></span></span>|
|<span data-ttu-id="a138a-758">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="a138a-758">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a138a-759">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-759"></span></span>|
|<span data-ttu-id="a138a-760">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a138a-760">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a138a-761">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-761"></span></span>|
|<span data-ttu-id="a138a-762">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a138a-762">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a138a-763">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-763"></span></span>|
|<span data-ttu-id="a138a-764">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="a138a-764">**CRL URLs**</span></span>|
|<span data-ttu-id="a138a-765">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-765"></span></span>|
|<span data-ttu-id="a138a-766">**OCSP の Url**</span><span class="sxs-lookup"><span data-stu-id="a138a-766">**OCSP URLs**</span></span>|
|<span data-ttu-id="a138a-767">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-767"></span></span>|
   
 <span data-ttu-id="a138a-768">**GlobalSign 組織検証の CA の SHA256 - G2**</span><span class="sxs-lookup"><span data-stu-id="a138a-768">**GlobalSign Organization Validation CA - SHA256 - G2**</span></span>
  
||
|:-----|
|<span data-ttu-id="a138a-769">**件名**</span><span class="sxs-lookup"><span data-stu-id="a138a-769">**Subject**</span></span>|
|<span data-ttu-id="a138a-770">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-770"></span></span>|
|<span data-ttu-id="a138a-771">**発行者**</span><span class="sxs-lookup"><span data-stu-id="a138a-771">**Issuer**</span></span>|
|<span data-ttu-id="a138a-772">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-772"></span></span>|
|<span data-ttu-id="a138a-773">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="a138a-773">**Serial Number**</span></span>|
|<span data-ttu-id="a138a-774">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-774"></span></span>|
|<span data-ttu-id="a138a-775">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="a138a-775">**Public Key Length**</span></span>|
|<span data-ttu-id="a138a-776">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-776"></span></span>|
|<span data-ttu-id="a138a-777">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="a138a-777">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a138a-778">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-778"></span></span>|
|<span data-ttu-id="a138a-779">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="a138a-779">**Validity Not Before**</span></span>|
|<span data-ttu-id="a138a-780">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-780"></span></span>|
|<span data-ttu-id="a138a-781">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="a138a-781">**Validity Not After**</span></span>|
|<span data-ttu-id="a138a-782">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-782"></span></span>|
|<span data-ttu-id="a138a-783">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a138a-783">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a138a-784">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-784"></span></span>|
|<span data-ttu-id="a138a-785">**機関キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a138a-785">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="a138a-786">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-786"></span></span>|
|<span data-ttu-id="a138a-787">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="a138a-787">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a138a-788">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-788"></span></span>|
|<span data-ttu-id="a138a-789">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a138a-789">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a138a-790">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-790"></span></span>|
|<span data-ttu-id="a138a-791">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a138a-791">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a138a-792">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-792"></span></span>|
|<span data-ttu-id="a138a-793">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="a138a-793">**CRL URLs**</span></span>|
|<span data-ttu-id="a138a-794">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-794"></span></span>|
|<span data-ttu-id="a138a-795">**OCSP の Url**</span><span class="sxs-lookup"><span data-stu-id="a138a-795">**OCSP URLs**</span></span>|
|<span data-ttu-id="a138a-796">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-796"></span></span>|
   
 <span data-ttu-id="a138a-797">**GlobalSign 組織検証の CA の SHA256 - G2**</span><span class="sxs-lookup"><span data-stu-id="a138a-797">**GlobalSign Organization Validation CA - SHA256 - G2**</span></span>
  
||
|:-----|
|<span data-ttu-id="a138a-798">**件名**</span><span class="sxs-lookup"><span data-stu-id="a138a-798">**Subject**</span></span>|
|<span data-ttu-id="a138a-799">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-799"></span></span>|
|<span data-ttu-id="a138a-800">**発行者**</span><span class="sxs-lookup"><span data-stu-id="a138a-800">**Issuer**</span></span>|
|<span data-ttu-id="a138a-801">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-801"></span></span>|
|<span data-ttu-id="a138a-802">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="a138a-802">**Serial Number**</span></span>|
|<span data-ttu-id="a138a-803">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-803"></span></span>|
|<span data-ttu-id="a138a-804">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="a138a-804">**Public Key Length**</span></span>|
|<span data-ttu-id="a138a-805">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-805"></span></span>|
|<span data-ttu-id="a138a-806">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="a138a-806">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a138a-807">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-807"></span></span>|
|<span data-ttu-id="a138a-808">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="a138a-808">**Validity Not Before**</span></span>|
|<span data-ttu-id="a138a-809">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-809"></span></span>|
|<span data-ttu-id="a138a-810">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="a138a-810">**Validity Not After**</span></span>|
|<span data-ttu-id="a138a-811">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-811"></span></span>|
|<span data-ttu-id="a138a-812">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a138a-812">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a138a-813">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-813"></span></span>|
|<span data-ttu-id="a138a-814">**機関キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a138a-814">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="a138a-815">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-815"></span></span>|
|<span data-ttu-id="a138a-816">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="a138a-816">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a138a-817">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-817"></span></span>|
|<span data-ttu-id="a138a-818">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a138a-818">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a138a-819">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-819"></span></span>|
|<span data-ttu-id="a138a-820">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a138a-820">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a138a-821">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-821"></span></span>|
|<span data-ttu-id="a138a-822">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="a138a-822">**CRL URLs**</span></span>|
|<span data-ttu-id="a138a-823">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-823"></span></span>|
|<span data-ttu-id="a138a-824">**OCSP の Url**</span><span class="sxs-lookup"><span data-stu-id="a138a-824">**OCSP URLs**</span></span>|
|<span data-ttu-id="a138a-825">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-825"></span></span>|
   
 <span data-ttu-id="a138a-826">**機関 X3 を暗号化してみましょう**</span><span class="sxs-lookup"><span data-stu-id="a138a-826">**Let's Encrypt Authority X3**</span></span>
  
||
|:-----|
|<span data-ttu-id="a138a-827">**件名**</span><span class="sxs-lookup"><span data-stu-id="a138a-827">**Subject**</span></span>|
|<span data-ttu-id="a138a-828">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-828"></span></span>|
|<span data-ttu-id="a138a-829">**発行者**</span><span class="sxs-lookup"><span data-stu-id="a138a-829">**Issuer**</span></span>|
|<span data-ttu-id="a138a-830">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-830"></span></span>|
|<span data-ttu-id="a138a-831">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="a138a-831">**Serial Number**</span></span>|
|<span data-ttu-id="a138a-832">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-832"></span></span>|
|<span data-ttu-id="a138a-833">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="a138a-833">**Public Key Length**</span></span>|
|<span data-ttu-id="a138a-834">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-834"></span></span>|
|<span data-ttu-id="a138a-835">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="a138a-835">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a138a-836">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-836"></span></span>|
|<span data-ttu-id="a138a-837">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="a138a-837">**Validity Not Before**</span></span>|
|<span data-ttu-id="a138a-838">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-838"></span></span>|
|<span data-ttu-id="a138a-839">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="a138a-839">**Validity Not After**</span></span>|
|<span data-ttu-id="a138a-840">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-840"></span></span>|
|<span data-ttu-id="a138a-841">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a138a-841">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a138a-842">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-842"></span></span>|
|<span data-ttu-id="a138a-843">**機関キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a138a-843">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="a138a-844">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-844"></span></span>|
|<span data-ttu-id="a138a-845">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="a138a-845">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a138a-846">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-846"></span></span>|
|<span data-ttu-id="a138a-847">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a138a-847">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a138a-848">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-848"></span></span>|
|<span data-ttu-id="a138a-849">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a138a-849">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a138a-850">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-850"></span></span>|
|<span data-ttu-id="a138a-851">**AIA の Url**</span><span class="sxs-lookup"><span data-stu-id="a138a-851">**AIA URLs**</span></span>|
|<span data-ttu-id="a138a-852">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-852"></span></span>|
|<span data-ttu-id="a138a-853">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="a138a-853">**CRL URLs**</span></span>|
|<span data-ttu-id="a138a-854">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-854"></span></span>|
|<span data-ttu-id="a138a-855">**OCSP の Url**</span><span class="sxs-lookup"><span data-stu-id="a138a-855">**OCSP URLs**</span></span>|
|<span data-ttu-id="a138a-856">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-856"></span></span>|
   
 <span data-ttu-id="a138a-857">**Microsoft IT の SSL SHA2**</span><span class="sxs-lookup"><span data-stu-id="a138a-857">**Microsoft IT SSL SHA2**</span></span>
  
||
|:-----|
|<span data-ttu-id="a138a-858">**件名**</span><span class="sxs-lookup"><span data-stu-id="a138a-858">**Subject**</span></span>|
|<span data-ttu-id="a138a-859">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-859"></span></span>|
|<span data-ttu-id="a138a-860">**発行者**</span><span class="sxs-lookup"><span data-stu-id="a138a-860">**Issuer**</span></span>|
|<span data-ttu-id="a138a-861">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-861"></span></span>|
|<span data-ttu-id="a138a-862">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="a138a-862">**Serial Number**</span></span>|
|<span data-ttu-id="a138a-863">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-863"></span></span>|
|<span data-ttu-id="a138a-864">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="a138a-864">**Public Key Length**</span></span>|
|<span data-ttu-id="a138a-865">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-865"></span></span>|
|<span data-ttu-id="a138a-866">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="a138a-866">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a138a-867">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-867"></span></span>|
|<span data-ttu-id="a138a-868">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="a138a-868">**Validity Not Before**</span></span>|
|<span data-ttu-id="a138a-869">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-869"></span></span>|
|<span data-ttu-id="a138a-870">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="a138a-870">**Validity Not After**</span></span>|
|<span data-ttu-id="a138a-871">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-871"></span></span>|
|<span data-ttu-id="a138a-872">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a138a-872">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a138a-873">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-873"></span></span>|
|<span data-ttu-id="a138a-874">**機関キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a138a-874">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="a138a-875">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-875"></span></span>|
|<span data-ttu-id="a138a-876">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="a138a-876">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a138a-877">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-877"></span></span>|
|<span data-ttu-id="a138a-878">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a138a-878">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a138a-879">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-879"></span></span>|
|<span data-ttu-id="a138a-880">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a138a-880">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a138a-881">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-881"></span></span>|
|<span data-ttu-id="a138a-882">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="a138a-882">**CRL URLs**</span></span>|
|<span data-ttu-id="a138a-883">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-883"></span></span>|
   
 <span data-ttu-id="a138a-884">**Microsoft IT の SSL SHA2**</span><span class="sxs-lookup"><span data-stu-id="a138a-884">**Microsoft IT SSL SHA2**</span></span>
  
||
|:-----|
|<span data-ttu-id="a138a-885">**件名**</span><span class="sxs-lookup"><span data-stu-id="a138a-885">**Subject**</span></span>|
|<span data-ttu-id="a138a-886">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-886"></span></span>|
|<span data-ttu-id="a138a-887">**発行者**</span><span class="sxs-lookup"><span data-stu-id="a138a-887">**Issuer**</span></span>|
|<span data-ttu-id="a138a-888">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-888"></span></span>|
|<span data-ttu-id="a138a-889">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="a138a-889">**Serial Number**</span></span>|
|<span data-ttu-id="a138a-890">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-890"></span></span>|
|<span data-ttu-id="a138a-891">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="a138a-891">**Public Key Length**</span></span>|
|<span data-ttu-id="a138a-892">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-892"></span></span>|
|<span data-ttu-id="a138a-893">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="a138a-893">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a138a-894">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-894"></span></span>|
|<span data-ttu-id="a138a-895">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="a138a-895">**Validity Not Before**</span></span>|
|<span data-ttu-id="a138a-896">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-896"></span></span>|
|<span data-ttu-id="a138a-897">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="a138a-897">**Validity Not After**</span></span>|
|<span data-ttu-id="a138a-898">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-898"></span></span>|
|<span data-ttu-id="a138a-899">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a138a-899">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a138a-900">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-900"></span></span>|
|<span data-ttu-id="a138a-901">**機関キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a138a-901">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="a138a-902">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-902"></span></span>|
|<span data-ttu-id="a138a-903">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="a138a-903">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a138a-904">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-904"></span></span>|
|<span data-ttu-id="a138a-905">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a138a-905">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a138a-906">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-906"></span></span>|
|<span data-ttu-id="a138a-907">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a138a-907">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a138a-908">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-908"></span></span>|
|<span data-ttu-id="a138a-909">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="a138a-909">**CRL URLs**</span></span>|
|<span data-ttu-id="a138a-910">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-910"></span></span>|
|<span data-ttu-id="a138a-911">**OCSP の Url**</span><span class="sxs-lookup"><span data-stu-id="a138a-911">**OCSP URLs**</span></span>|
|<span data-ttu-id="a138a-912">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-912"></span></span>|
   
 <span data-ttu-id="a138a-913">**Microsoft IT の TLS の CA 1**</span><span class="sxs-lookup"><span data-stu-id="a138a-913">**Microsoft IT TLS CA 1**</span></span>
  
||
|:-----|
|<span data-ttu-id="a138a-914">**件名**</span><span class="sxs-lookup"><span data-stu-id="a138a-914">**Subject**</span></span>|
|<span data-ttu-id="a138a-915">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-915"></span></span>|
|<span data-ttu-id="a138a-916">**発行者**</span><span class="sxs-lookup"><span data-stu-id="a138a-916">**Issuer**</span></span>|
|<span data-ttu-id="a138a-917">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-917"></span></span>|
|<span data-ttu-id="a138a-918">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="a138a-918">**Serial Number**</span></span>|
|<span data-ttu-id="a138a-919">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-919"></span></span>|
|<span data-ttu-id="a138a-920">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="a138a-920">**Public Key Length**</span></span>|
|<span data-ttu-id="a138a-921">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-921"></span></span>|
|<span data-ttu-id="a138a-922">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="a138a-922">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a138a-923">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-923"></span></span>|
|<span data-ttu-id="a138a-924">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="a138a-924">**Validity Not Before**</span></span>|
|<span data-ttu-id="a138a-925">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-925"></span></span>|
|<span data-ttu-id="a138a-926">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="a138a-926">**Validity Not After**</span></span>|
|<span data-ttu-id="a138a-927">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-927"></span></span>|
|<span data-ttu-id="a138a-928">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a138a-928">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a138a-929">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-929"></span></span>|
|<span data-ttu-id="a138a-930">**機関キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a138a-930">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="a138a-931">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-931"></span></span>|
|<span data-ttu-id="a138a-932">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="a138a-932">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a138a-933">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-933"></span></span>|
|<span data-ttu-id="a138a-934">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a138a-934">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a138a-935">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-935"></span></span>|
|<span data-ttu-id="a138a-936">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a138a-936">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a138a-937">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-937"></span></span>|
|<span data-ttu-id="a138a-938">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="a138a-938">**CRL URLs**</span></span>|
|<span data-ttu-id="a138a-939">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-939"></span></span>|
|<span data-ttu-id="a138a-940">**OCSP の Url**</span><span class="sxs-lookup"><span data-stu-id="a138a-940">**OCSP URLs**</span></span>|
|<span data-ttu-id="a138a-941">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-941"></span></span>|
   
 <span data-ttu-id="a138a-942">**Microsoft IT TLS CA 2**</span><span class="sxs-lookup"><span data-stu-id="a138a-942">**Microsoft IT TLS CA 2**</span></span>
  
||
|:-----|
|<span data-ttu-id="a138a-943">**件名**</span><span class="sxs-lookup"><span data-stu-id="a138a-943">**Subject**</span></span>|
|<span data-ttu-id="a138a-944">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-944"></span></span>|
|<span data-ttu-id="a138a-945">**発行者**</span><span class="sxs-lookup"><span data-stu-id="a138a-945">**Issuer**</span></span>|
|<span data-ttu-id="a138a-946">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-946"></span></span>|
|<span data-ttu-id="a138a-947">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="a138a-947">**Serial Number**</span></span>|
|<span data-ttu-id="a138a-948">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-948"></span></span>|
|<span data-ttu-id="a138a-949">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="a138a-949">**Public Key Length**</span></span>|
|<span data-ttu-id="a138a-950">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-950"></span></span>|
|<span data-ttu-id="a138a-951">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="a138a-951">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a138a-952">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-952"></span></span>|
|<span data-ttu-id="a138a-953">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="a138a-953">**Validity Not Before**</span></span>|
|<span data-ttu-id="a138a-954">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-954"></span></span>|
|<span data-ttu-id="a138a-955">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="a138a-955">**Validity Not After**</span></span>|
|<span data-ttu-id="a138a-956">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-956"></span></span>|
|<span data-ttu-id="a138a-957">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a138a-957">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a138a-958">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-958"></span></span>|
|<span data-ttu-id="a138a-959">**機関キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a138a-959">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="a138a-960">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-960"></span></span>|
|<span data-ttu-id="a138a-961">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="a138a-961">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a138a-962">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-962"></span></span>|
|<span data-ttu-id="a138a-963">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a138a-963">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a138a-964">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-964"></span></span>|
|<span data-ttu-id="a138a-965">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a138a-965">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a138a-966">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-966"></span></span>|
|<span data-ttu-id="a138a-967">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="a138a-967">**CRL URLs**</span></span>|
|<span data-ttu-id="a138a-968">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-968"></span></span>|
|<span data-ttu-id="a138a-969">**OCSP の Url**</span><span class="sxs-lookup"><span data-stu-id="a138a-969">**OCSP URLs**</span></span>|
|<span data-ttu-id="a138a-970">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-970"></span></span>|
   
 <span data-ttu-id="a138a-971">**Microsoft IT TLS CA 4**</span><span class="sxs-lookup"><span data-stu-id="a138a-971">**Microsoft IT TLS CA 4**</span></span>
  
||
|:-----|
|<span data-ttu-id="a138a-972">**件名**</span><span class="sxs-lookup"><span data-stu-id="a138a-972">**Subject**</span></span>|
|<span data-ttu-id="a138a-973">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-973"></span></span>|
|<span data-ttu-id="a138a-974">**発行者**</span><span class="sxs-lookup"><span data-stu-id="a138a-974">**Issuer**</span></span>|
|<span data-ttu-id="a138a-975">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-975"></span></span>|
|<span data-ttu-id="a138a-976">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="a138a-976">**Serial Number**</span></span>|
|<span data-ttu-id="a138a-977">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-977"></span></span>|
|<span data-ttu-id="a138a-978">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="a138a-978">**Public Key Length**</span></span>|
|<span data-ttu-id="a138a-979">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-979"></span></span>|
|<span data-ttu-id="a138a-980">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="a138a-980">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a138a-981">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-981"></span></span>|
|<span data-ttu-id="a138a-982">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="a138a-982">**Validity Not Before**</span></span>|
|<span data-ttu-id="a138a-983">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-983"></span></span>|
|<span data-ttu-id="a138a-984">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="a138a-984">**Validity Not After**</span></span>|
|<span data-ttu-id="a138a-985">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-985"></span></span>|
|<span data-ttu-id="a138a-986">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a138a-986">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a138a-987">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-987"></span></span>|
|<span data-ttu-id="a138a-988">**機関キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a138a-988">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="a138a-989">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-989"></span></span>|
|<span data-ttu-id="a138a-990">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="a138a-990">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a138a-991">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-991"></span></span>|
|<span data-ttu-id="a138a-992">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a138a-992">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a138a-993">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-993"></span></span>|
|<span data-ttu-id="a138a-994">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a138a-994">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a138a-995">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-995"></span></span>|
|<span data-ttu-id="a138a-996">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="a138a-996">**CRL URLs**</span></span>|
|<span data-ttu-id="a138a-997">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-997"></span></span>|
|<span data-ttu-id="a138a-998">**OCSP の Url**</span><span class="sxs-lookup"><span data-stu-id="a138a-998">**OCSP URLs**</span></span>|
|<span data-ttu-id="a138a-999">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-999"></span></span>|
   
 <span data-ttu-id="a138a-1000">**Microsoft IT TLS CA 5**</span><span class="sxs-lookup"><span data-stu-id="a138a-1000">**Microsoft IT TLS CA 5**</span></span>
  
||
|:-----|
|<span data-ttu-id="a138a-1001">**件名**</span><span class="sxs-lookup"><span data-stu-id="a138a-1001">**Subject**</span></span>|
|<span data-ttu-id="a138a-1002">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-1002"></span></span>|
|<span data-ttu-id="a138a-1003">**発行者**</span><span class="sxs-lookup"><span data-stu-id="a138a-1003">**Issuer**</span></span>|
|<span data-ttu-id="a138a-1004">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-1004"></span></span>|
|<span data-ttu-id="a138a-1005">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="a138a-1005">**Serial Number**</span></span>|
|<span data-ttu-id="a138a-1006">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-1006"></span></span>|
|<span data-ttu-id="a138a-1007">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="a138a-1007">**Public Key Length**</span></span>|
|<span data-ttu-id="a138a-1008">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-1008"></span></span>|
|<span data-ttu-id="a138a-1009">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="a138a-1009">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a138a-1010">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-1010"></span></span>|
|<span data-ttu-id="a138a-1011">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="a138a-1011">**Validity Not Before**</span></span>|
|<span data-ttu-id="a138a-1012">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-1012"></span></span>|
|<span data-ttu-id="a138a-1013">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="a138a-1013">**Validity Not After**</span></span>|
|<span data-ttu-id="a138a-1014">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-1014"></span></span>|
|<span data-ttu-id="a138a-1015">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a138a-1015">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a138a-1016">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-1016"></span></span>|
|<span data-ttu-id="a138a-1017">**機関キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a138a-1017">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="a138a-1018">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-1018"></span></span>|
|<span data-ttu-id="a138a-1019">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="a138a-1019">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a138a-1020">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-1020"></span></span>|
|<span data-ttu-id="a138a-1021">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a138a-1021">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a138a-1022">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-1022"></span></span>|
|<span data-ttu-id="a138a-1023">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a138a-1023">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a138a-1024">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-1024"></span></span>|
|<span data-ttu-id="a138a-1025">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="a138a-1025">**CRL URLs**</span></span>|
|<span data-ttu-id="a138a-1026">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-1026"></span></span>|
|<span data-ttu-id="a138a-1027">**OCSP の Url**</span><span class="sxs-lookup"><span data-stu-id="a138a-1027">**OCSP URLs**</span></span>|
|<span data-ttu-id="a138a-1028">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-1028"></span></span>|
   
 <span data-ttu-id="a138a-1029">**Symantec クラス 3 の EV SSL CA G3**</span><span class="sxs-lookup"><span data-stu-id="a138a-1029">**Symantec Class 3 EV SSL CA - G3**</span></span>
  
||
|:-----|
|<span data-ttu-id="a138a-1030">**件名**</span><span class="sxs-lookup"><span data-stu-id="a138a-1030">**Subject**</span></span>|
|<span data-ttu-id="a138a-1031">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-1031"></span></span>|
|<span data-ttu-id="a138a-1032">**発行者**</span><span class="sxs-lookup"><span data-stu-id="a138a-1032">**Issuer**</span></span>|
|<span data-ttu-id="a138a-1033">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-1033"></span></span>|
|<span data-ttu-id="a138a-1034">**代わりのサブジェクト名**</span><span class="sxs-lookup"><span data-stu-id="a138a-1034">**Subject Alternative Name**</span></span>|
|<span data-ttu-id="a138a-1035">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-1035"></span></span>|
|<span data-ttu-id="a138a-1036">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="a138a-1036">**Serial Number**</span></span>|
|<span data-ttu-id="a138a-1037">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-1037"></span></span>|
|<span data-ttu-id="a138a-1038">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="a138a-1038">**Public Key Length**</span></span>|
|<span data-ttu-id="a138a-1039">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-1039"></span></span>|
|<span data-ttu-id="a138a-1040">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="a138a-1040">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a138a-1041">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-1041"></span></span>|
|<span data-ttu-id="a138a-1042">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="a138a-1042">**Validity Not Before**</span></span>|
|<span data-ttu-id="a138a-1043">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-1043"></span></span>|
|<span data-ttu-id="a138a-1044">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="a138a-1044">**Validity Not After**</span></span>|
|<span data-ttu-id="a138a-1045">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-1045"></span></span>|
|<span data-ttu-id="a138a-1046">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a138a-1046">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a138a-1047">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-1047"></span></span>|
|<span data-ttu-id="a138a-1048">**機関キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a138a-1048">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="a138a-1049">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-1049"></span></span>|
|<span data-ttu-id="a138a-1050">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="a138a-1050">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a138a-1051">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-1051"></span></span>|
|<span data-ttu-id="a138a-1052">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a138a-1052">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a138a-1053">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-1053"></span></span>|
|<span data-ttu-id="a138a-1054">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a138a-1054">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a138a-1055">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-1055"></span></span>|
|<span data-ttu-id="a138a-1056">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="a138a-1056">**CRL URLs**</span></span>|
|<span data-ttu-id="a138a-1057">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-1057"></span></span>|
|<span data-ttu-id="a138a-1058">**OCSP の Url**</span><span class="sxs-lookup"><span data-stu-id="a138a-1058">**OCSP URLs**</span></span>|
|<span data-ttu-id="a138a-1059">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-1059"></span></span>|
   
 <span data-ttu-id="a138a-1060">**Symantec クラス 3 セキュリティで保護されたサーバー CA - 第 4 世代**</span><span class="sxs-lookup"><span data-stu-id="a138a-1060">**Symantec Class 3 Secure Server CA - G4**</span></span>
  
||
|:-----|
|<span data-ttu-id="a138a-1061">**件名**</span><span class="sxs-lookup"><span data-stu-id="a138a-1061">**Subject**</span></span>|
|<span data-ttu-id="a138a-1062">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-1062"></span></span>|
|<span data-ttu-id="a138a-1063">**発行者**</span><span class="sxs-lookup"><span data-stu-id="a138a-1063">**Issuer**</span></span>|
|<span data-ttu-id="a138a-1064">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-1064"></span></span>|
|<span data-ttu-id="a138a-1065">**代わりのサブジェクト名**</span><span class="sxs-lookup"><span data-stu-id="a138a-1065">**Subject Alternative Name**</span></span>|
|<span data-ttu-id="a138a-1066">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-1066"></span></span>|
|<span data-ttu-id="a138a-1067">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="a138a-1067">**Serial Number**</span></span>|
|<span data-ttu-id="a138a-1068">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-1068"></span></span>|
|<span data-ttu-id="a138a-1069">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="a138a-1069">**Public Key Length**</span></span>|
|<span data-ttu-id="a138a-1070">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-1070"></span></span>|
|<span data-ttu-id="a138a-1071">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="a138a-1071">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a138a-1072">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-1072"></span></span>|
|<span data-ttu-id="a138a-1073">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="a138a-1073">**Validity Not Before**</span></span>|
|<span data-ttu-id="a138a-1074">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-1074"></span></span>|
|<span data-ttu-id="a138a-1075">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="a138a-1075">**Validity Not After**</span></span>|
|<span data-ttu-id="a138a-1076">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-1076"></span></span>|
|<span data-ttu-id="a138a-1077">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a138a-1077">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a138a-1078">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-1078"></span></span>|
|<span data-ttu-id="a138a-1079">**機関キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a138a-1079">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="a138a-1080">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-1080"></span></span>|
|<span data-ttu-id="a138a-1081">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="a138a-1081">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a138a-1082">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-1082"></span></span>|
|<span data-ttu-id="a138a-1083">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a138a-1083">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a138a-1084">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-1084"></span></span>|
|<span data-ttu-id="a138a-1085">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a138a-1085">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a138a-1086">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-1086"></span></span>|
|<span data-ttu-id="a138a-1087">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="a138a-1087">**CRL URLs**</span></span>|
|<span data-ttu-id="a138a-1088">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-1088"></span></span>|
|<span data-ttu-id="a138a-1089">**OCSP の Url**</span><span class="sxs-lookup"><span data-stu-id="a138a-1089">**OCSP URLs**</span></span>|
|<span data-ttu-id="a138a-1090">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-1090"></span></span>|
   
 <span data-ttu-id="a138a-1091">**thawte SHA256 SSL CA**</span><span class="sxs-lookup"><span data-stu-id="a138a-1091">**thawte SHA256 SSL CA**</span></span>
  
||
|:-----|
|<span data-ttu-id="a138a-1092">**件名**</span><span class="sxs-lookup"><span data-stu-id="a138a-1092">**Subject**</span></span>|
|<span data-ttu-id="a138a-1093">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-1093"></span></span>|
|<span data-ttu-id="a138a-1094">**発行者**</span><span class="sxs-lookup"><span data-stu-id="a138a-1094">**Issuer**</span></span>|
|<span data-ttu-id="a138a-1095">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-1095"></span></span>|
|<span data-ttu-id="a138a-1096">**代わりのサブジェクト名**</span><span class="sxs-lookup"><span data-stu-id="a138a-1096">**Subject Alternative Name**</span></span>|
|<span data-ttu-id="a138a-1097">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-1097"></span></span>|
|<span data-ttu-id="a138a-1098">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="a138a-1098">**Serial Number**</span></span>|
|<span data-ttu-id="a138a-1099">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-1099"></span></span>|
|<span data-ttu-id="a138a-1100">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="a138a-1100">**Public Key Length**</span></span>|
|<span data-ttu-id="a138a-1101">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-1101"></span></span>|
|<span data-ttu-id="a138a-1102">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="a138a-1102">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a138a-1103">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-1103"></span></span>|
|<span data-ttu-id="a138a-1104">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="a138a-1104">**Validity Not Before**</span></span>|
|<span data-ttu-id="a138a-1105">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-1105"></span></span>|
|<span data-ttu-id="a138a-1106">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="a138a-1106">**Validity Not After**</span></span>|
|<span data-ttu-id="a138a-1107">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-1107"></span></span>|
|<span data-ttu-id="a138a-1108">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a138a-1108">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a138a-1109">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-1109"></span></span>|
|<span data-ttu-id="a138a-1110">**機関キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a138a-1110">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="a138a-1111">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-1111"></span></span>|
|<span data-ttu-id="a138a-1112">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="a138a-1112">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a138a-1113">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-1113"></span></span>|
|<span data-ttu-id="a138a-1114">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a138a-1114">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a138a-1115">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-1115"></span></span>|
|<span data-ttu-id="a138a-1116">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a138a-1116">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a138a-1117">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-1117"></span></span>|
|<span data-ttu-id="a138a-1118">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="a138a-1118">**CRL URLs**</span></span>|
|<span data-ttu-id="a138a-1119">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-1119"></span></span>|
|<span data-ttu-id="a138a-1120">**OCSP の Url**</span><span class="sxs-lookup"><span data-stu-id="a138a-1120">**OCSP URLs**</span></span>|
|<span data-ttu-id="a138a-1121">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-1121"></span></span>|
   
 <span data-ttu-id="a138a-1122">**Verizon akamai 社 SureServer CA G14-SHA2**</span><span class="sxs-lookup"><span data-stu-id="a138a-1122">**Verizon Akamai SureServer CA G14-SHA2**</span></span>
  
||
|:-----|
|<span data-ttu-id="a138a-1123">**件名**</span><span class="sxs-lookup"><span data-stu-id="a138a-1123">**Subject**</span></span>|
|<span data-ttu-id="a138a-1124">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-1124"></span></span>|
|<span data-ttu-id="a138a-1125">**発行者**</span><span class="sxs-lookup"><span data-stu-id="a138a-1125">**Issuer**</span></span>|
|<span data-ttu-id="a138a-1126">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-1126"></span></span>|
|<span data-ttu-id="a138a-1127">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="a138a-1127">**Serial Number**</span></span>|
|<span data-ttu-id="a138a-1128">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-1128"></span></span>|
|<span data-ttu-id="a138a-1129">**公開キーの長さ**</span><span class="sxs-lookup"><span data-stu-id="a138a-1129">**Public Key Length**</span></span>|
|<span data-ttu-id="a138a-1130">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-1130"></span></span>|
|<span data-ttu-id="a138a-1131">**署名アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="a138a-1131">**Signature Algorithm**</span></span>|
|<span data-ttu-id="a138a-1132">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-1132"></span></span>|
|<span data-ttu-id="a138a-1133">**以前の有効性**</span><span class="sxs-lookup"><span data-stu-id="a138a-1133">**Validity Not Before**</span></span>|
|<span data-ttu-id="a138a-1134">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-1134"></span></span>|
|<span data-ttu-id="a138a-1135">**有効期間終了**</span><span class="sxs-lookup"><span data-stu-id="a138a-1135">**Validity Not After**</span></span>|
|<span data-ttu-id="a138a-1136">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-1136"></span></span>|
|<span data-ttu-id="a138a-1137">**サブジェクト キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a138a-1137">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="a138a-1138">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-1138"></span></span>|
|<span data-ttu-id="a138a-1139">**機関キー識別子**</span><span class="sxs-lookup"><span data-stu-id="a138a-1139">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="a138a-1140">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-1140"></span></span>|
|<span data-ttu-id="a138a-1141">**拇印 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="a138a-1141">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="a138a-1142">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-1142"></span></span>|
|<span data-ttu-id="a138a-1143">**拇印 (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a138a-1143">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="a138a-1144">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-1144"></span></span>|
|<span data-ttu-id="a138a-1145">**暗証番号 (pin) (sha-256)**</span><span class="sxs-lookup"><span data-stu-id="a138a-1145">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="a138a-1146">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-1146"></span></span>|
|<span data-ttu-id="a138a-1147">**AIA の Url**</span><span class="sxs-lookup"><span data-stu-id="a138a-1147">**AIA URLs**</span></span>|
|<span data-ttu-id="a138a-1148">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-1148"></span></span>|
|<span data-ttu-id="a138a-1149">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="a138a-1149">**CRL URLs**</span></span>|
|<span data-ttu-id="a138a-1150">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-1150"></span></span>|
|<span data-ttu-id="a138a-1151">**OCSP の Url**</span><span class="sxs-lookup"><span data-stu-id="a138a-1151">**OCSP URLs**</span></span>|
|<span data-ttu-id="a138a-1152">:-----</span><span class="sxs-lookup"><span data-stu-id="a138a-1152"></span></span>|
   
## <a name="additional-certificate-paths"></a><span data-ttu-id="a138a-1153">追加の証明書のパス</span><span class="sxs-lookup"><span data-stu-id="a138a-1153">Additional certificate paths</span></span>
<span data-ttu-id="a138a-1154"><a name="IntermediateCerts"> </a></span><span class="sxs-lookup"><span data-stu-id="a138a-1154"></span></span>

<span data-ttu-id="a138a-1155">次には、上は含まれていないし、時間の経過と共に上のリストと結合されている従来の証明書が含まれます。</span><span class="sxs-lookup"><span data-stu-id="a138a-1155">The following include legacy certificates that aren't included above and will be merged with the list above over time.</span></span>
  
```
evsecure-aia.verisign.com
sa.symcb.com
sd.symcb.com
*.omniroot.com
*.verisign.com
*.symcb.com
*.symcd.com
*.verisign.net
*.geotrust.com
*.entrust.net
*.public-trust.com
EVIntl-ocsp.verisign.com
EVSecure-ocsp.verisign.com
isrg.trustid.ocsp.identrust.com
ocsp.digicert.com
ocsp.entrust.net
ocsp.globalsign.com/ExtendedSSLSHA256CACross
ocsp.globalsign.com/rootr1
ocsp.globalsign.com/rootr2
ocsp2.globalsign.com/rootr3
ocsp.int-x3.letsencrypt.org/
ocsp.msocsp.com
ocsp.omniroot.com/baltimoreroot
ocsp2.globalsign.com/gsextendvalsha2g3r3
ocsp2.globalsign.com/gsorganizationvalsha2g2
ocsp2.globalsign.com/gsorganizationvalsha2g3
ocsp2.globalsign.com/rootr3
ocspx.digicert.com
s2.symcb.com
sr.symcd.com
su.symcd.com
vassg142.ocsp.omniroot.com
cdp1.public-trust.com/CRL/Omniroot2025.crl
crl.entrust.net/2048ca.crl
crl.entrust.net/g2ca.crl
crl.entrust.net/level1k.crl
crl.entrust.net/rootca1.crl
crl.globalsign.com/gs/gsextendvalsha2g3r3.crl
crl.globalsign.com/gs/gsorganizationvalsha2g2.crl
crl.globalsign.com/gsorganizationvalsha2g3.crl
crl.globalsign.com/root.crl
crl.globalsign.net/root-r2.crl
crl.globalsign.com/root-r3.crl
crl.globalsign.net/root.crl
crl.identrust.com/DSTROOTCAX3CRL.crl
crl.microsoft.com/pki/mscorp/crl/msitwww1.crl
crl.microsoft.com/pki/mscorp/crl/msitwww2.crl
crl3.digicert.com/DigiCertCloudServicesCA-1-g1.crl
crl3.digicert.com/DigiCertGlobalRootCA.crl
crl3.digicert.com/sha2-ev-server-g1.crl
crl3.digicert.com/sha2-ha-server-g5.crl
crl3.digicert.com/ssca-sha2-g5.crl
crl4.digicert.com/DigiCertCloudServicesCA-1-g1.crl
crl4.digicert.com/DigiCertGlobalRootCA.crl
crl4.digicert.com/DigiCertHighAssuranceEVRootCA.crl
crl4.digicert.com/sha2-ev-server-g1.crl
crl4.digicert.com/sha2-ha-server-g5.crl
crl4.digicert.com/ssca-sha2-g5.crl
EVIntl-crl.verisign.com/EVIntl2006.crl
EVSecure-crl.verisign.com/pca3-g5.crl
mscrl.microsoft.com/pki/mscorp/crl/msitwww1.crl
mscrl.microsoft.com/pki/mscorp/crl/msitwww2.crl
s1.symcb.com/pca3-g5.crl
sr.symcb.com/sr.crl
su.symcb.com/su.crl
vassg142.crl.omniroot.com/vassg142.crl
aia.entrust.net/l1k-chain256.cer
apps.identrust.com/roots/dstrootcax3.p7c
https://cacert.a.omniroot.com/vassg142.crt
https://cacert.a.omniroot.com/vassg142.der
https://cacert.omniroot.com/baltimoreroot.crt
https://cacert.omniroot.com/baltimoreroot.der
cacerts.digicert.com/DigiCertCloudServicesCA-1.crt
cacerts.digicert.com/DigiCertSHA2ExtendedValidationServerCA.crt
cacerts.digicert.com/DigiCertSHA2HighAssuranceServerCA.crt
cacerts.digicert.com/DigiCertSHA2SecureServerCA.crt
cert.int-x3.letsencrypt.org/
EVIntl-aia.verisign.com/EVIntl2006.cer
secure.globalsign.com/cacert/gsextendvalsha2g2r2.crt
secure.globalsign.com/cacert/gsextendvalsha2g3r3.crt
secure.globalsign.com/cacert/gsorganizationvalsha2g2r1.crt
secure.globalsign.com/cacert/gsorganizationvalsha2g3.crt
sr.symcb.com/sr.crt
su.symcb.com/su.crt
https://www.digicert.com/CACerts/DigiCertGlobalRootCA.crt
https://www.digicert.com/CACerts/DigiCertHighAssuranceEVRootCA.crt
www.microsoft.com/pki/mscorp/msitwww1.crt
www.microsoft.com/pki/mscorp/msitwww2.crt

```


