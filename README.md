# Authorize.net

Basic abstraction with Laravel integration for Authorize.net
 
 ## Notice
 
 Namespace of package has been updated from `Pseudocody` to `Codylewis` to reflect github name update, this is a one time change.
 
### Installation

- `composer require codylewis/authorizenet`
- For Laravel 5 support:
    - Add the service provider to `config/app.php`: `Codylewis\AuthorizeNet\AuthorizeNetServiceProvider`
    - Register the facade: `'AuthorizeNet' => Codylewis\AuthorizeNet\AuthorizeNetFacade::class,`
    - Add `.env` value for `AUTHORIZE_NET_LOGIN` (Login ID) and `AUTHORIZE_NET_TRANSACTION_KEY` (Transaction Key)
    - Optionally create the config file: `config/authorizenet.php`
    
### Usage
- Within Laravel 5, instantiate using the API key in the constructor: `$authorizeNet = new Codylewis\AuthorizeNet\AuthorizeNet($loginId, $transactionKey)`
- `AuthorizeNet::authorizeCreditCard($order)` attempts authorize cards with provided information, returns response
- `AuthorizeNet::capturePreviouslyAuthorizedCreditcard($transactionId, $amount)` attempts to capture previously authorized credit card

