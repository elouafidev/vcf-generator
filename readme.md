# VCF Generator for Laravel

[![Latest Version on Packagist](https://img.shields.io/packagist/v/elouafidev/vcf-generator.svg?style=flat-square)](https://packagist.org/packages/elouafidev/vcf-generator)
[![Total Downloads](https://img.shields.io/packagist/dt/elouafidev/vcf-generator.svg?style=flat-square)](https://packagist.org/packages/elouafidev/vcf-generator)
[![License](https://img.shields.io/packagist/l/elouafidev/vcf-generator.svg?style=flat-square)](https://packagist.org/packages/elouafidev/vcf-generator)

A simple VCF (vCard) generator for Laravel. This package provides an easy way to generate VCF files for contacts in your Laravel applications. It supports adding various contact details such as full name, email addresses, phone numbers, addresses, social media profiles, and more.

## Installation

You can install the package via composer:

```bash
composer require elouafidev/vcf-generator
```

## Usage

Here is a simple example of how to use the VCF generator in your Laravel project:

```php
use ElouafiDev\VCFGenerator\VCFGenerator;

$vcf = new VCFGenerator();
$vcf->setFullName('John Doe')
    ->setEmail('john.doe@example.com', VCFGenerator::WORK)
    ->setPhoneNumber('+123456789', VCFGenerator::WORK)
    ->setAddress('123 Main St, Anytown, USA')
    ->setTitle('Software Engineer')
    ->setDescription('Experienced software engineer with a passion for developing innovative programs.')
    ->setProfileImage150x150('/path/to/image.png')
    ->setFacebook('https://facebook.com/johndoe')
    ->setTwitter('https://twitter.com/johndoe')
    ->setLinkedin('https://linkedin.com/in/johndoe')
    ->setYoutube('https://youtube.com/johndoe')
    ->setInstagram('https://instagram.com/johndoe')
    ->setWebsite('https://johndoe.com')
    ->setSkype('johndoe');

return $vcf->download();
```

### Methods

- `setFullName(string $full_name): self`
- `setEmail(string $email, string $type): self`
- `setPhoneNumber(string $phone, string $type): self`
- `setAddress(string $address): self`
- `setTitle(string $title): self`
- `setDescription(string $description): self`
- `setProfileImage150x150(string $profile_image_150x150): self`
- `setFacebook(string $url): self`
- `setTwitter(string $url): self`
- `setLinkedin(string $url): self`
- `setYoutube(string $url): self`
- `setInstagram(string $url): self`
- `setWebsite(string $url): self`
- `setSkype(string $url): self`
- `vcfContent(): string`
- `toBase64(): string`
- `toUri(): string`
- `download()`
- `validateEmail(string $email): bool`
- `validatePhoneNumber(string $phone): bool`
- `clear(): self`
- `setAttributes(array $attributes): self`

### Examples

#### Generate VCF Content

```php
$vcfContent = $vcf->vcfContent();
echo $vcfContent;
```

#### Get VCF as Base64

```php
$vcfBase64 = $vcf->toBase64();
echo $vcfBase64;
```

#### Get VCF as Data URI

```php
$vcfUri = $vcf->toUri();
echo $vcfUri;
```

## Contributing

Please see [CONTRIBUTING](CONTRIBUTING.md) for details.

## License

The MIT License (MIT). Please see [License File](LICENSE.md) for more information.

## Author

Mouad Elouafi
- Email: support@elouafi.dev