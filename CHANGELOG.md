# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](http://keepachangelog.com/en/1.0.0/)
and this project adheres to [Semantic Versioning](http://semver.org/spec/v2.0.0.html).

## [7.0.0] - 2025-09-30
### Added
 - Maintained fork established by HCS-LLC.
 - Added support for php 8.4
 - Added strict parameter and return types throughout the library.

### Changed
 - **BREAKING:** Dropped support for PHP versions older than 7.4. The new requirement is `^7.4 || ^8.0`.
 - Modernized codebase to use PHP 7.4+ features.
 - Updated development dependencies, including PHPUnit to version 9.5.

### Removed
 - **BREAKING:** Support for PHP 7.0, 7.1, 7.2, and 7.3.

## [6.1.0] - 2020-02-28
### Added
 - The "Client::preEncode" and "Client::postDecode" methods have been added to allow
   advanced users to inspect and tweak the inner workings of the JSON-RPC library.
 - The "Server::rawReply" method has been added to complement the new "Client" methods.

## [6.0.0] - 2019-07-25
### Changed
 - There are now two types of responses--an "ErrorResponse" and a "ResultResponse"--
   which both derive from a base "Response" class. The "Client::decode" method
   returns a list of these "Response" objects. You can use the "instanceof"
   type operator to see which type of response you have received.

## [5.0.0] - 2018-05-16
### Added
 - The "Client::decode" method now throws an "ErrorException" when the input is not a valid JSON-RPC 2.0 reply string
 - The "Client::query" and "Client::notify" methods now return the object handle, so you can chain method calls if you like

### Changed
 - The "Client::decode" method now returns a list of "Response" objects (rather than an associative array of raw JSON-RPC 2.0 keys and values)
 - The four exception classes have been moved (e.g. "Datto\JsonRpc\Exception\Application" => "Datto\JsonRpc\Exception**s**\\**Application**Exception")
