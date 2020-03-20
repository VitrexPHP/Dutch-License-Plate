# Dutch-License-Plate
Formats Dutch Car License Plate

```php
<?php
function formatLicensePlate(string $license = '64GZB8'): string
function formatLicensePlate(string $license = '64GZB8'): string
{
	if (preg_match('/^([A-Z]*)([\d]*)([A-Z]*)([\d]*)/i', $license, $matches) === false) {
		return $license;
	}
	$parts = [];
	for ($i = 1, $iMax = count($matches); $i < $iMax; $i++) {
		$parts[] = strlen($matches[ $i ]) === 4 ? str_split($matches[ $i ], 2) : [$matches[ $i ]];
	}
	
	return strtoupper(implode('-', array_filter(array_merge(...$parts))));
}
?>
```
