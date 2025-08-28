# Complete Merchant KYC

Submit KYC documents for merchant registration.

*   **Endpoint**: `PUT {{base-url}}/merchant/complete-merchant-registration`
    
*   **Body** (form-data):
    
    *   `cac_pack`: File (e.g., `/C:/herlabytes/Medilog/src/assets/images/avatar.png`)
        
    *   `directorsBVN`: BVN number (e.g., `22192640723`)
        
    *   `merchantId`: Merchant ID (e.g., `2c5356fc-1127-4e67-a001-2ae170731bee`)
        
    
*   **Response**:
    
    *   **200 OK**:

        ```
        {
          "status": true,
          "message": "Your Documents have been uploaded and Pending Review"
        }
        ```
        
    
*   **Sample Code (Dart)**:

    ```
    var request = http.MultipartRequest('PUT', Uri.parse('{{base-url}}/merchant/complete-merchant-registration'));
    request.fields.addAll({
      'directorsBVN': '22222222226',
      'merchantId': '46791573-12d5-4f65-9868-f09a6a18aa74'
    });
    request.files.add(await http.MultipartFile.fromPath('cac_pack', '/Users/Herlarbs/Downloads/Bleyt Glide Development Scope.pdf'));
    http.StreamedResponse response = await request.send();
    if (response.statusCode == 200) {
      print(await response.stream.bytesToString());
    } else {
      print(response.reasonPhrase);
    }
    ```
    

[PreviousResend Verification Code](/xpress-wallet-api/merchant/resend-verification-code)[NextGet Merchant Profile](/xpress-wallet-api/merchant/get-merchant-profile)

Last updated 26 days ago