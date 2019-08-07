# คลีนโค้ด PHP

## สารบัญ  

  1. [บทนำ](#คำนำ)
  2. [ตัวแปร](#ตัวแปร)
     * [ใช้ชื่อตัวแปรที่มีความหมายและอ่านออกเสียงได้](#ใช้ชื่อตัวแปรที่มีความหมายและอ่านออกเสียงได้)
     * [ใช้ศัพท์เดียวกันสำหรับตัวแปรชนิดเดียวกัน](#ใช้ศัพท์เดียวกันสำหรับตัวแปรชนิดเดียวกัน)
     * [ใช้ชื่อที่ค้นหาเจอได้ (ภาค 1)](#ใช้ชื่อที่ค้นหาเจอได้ (ภาค 1))
     * [ใช้ชื่อที่ค้นหาเจอได้ (ภาค 2)](#ใช้ชื่อที่ค้นหาเจอได้ (ภาค 2))
     * [ใช้ตัวแปรที่อธิบายตัวเองได้](#ใช้ตัวแปรที่อธิบายตัวเองได้)
     * [หลีกเลี่ยงโค้ดที่ซ้อนลงไปลึกเกินไปและคืนค่าตั้งแต่ต้น (ภาค 1)](#หลีกเลี่ยงโค้ดที่ซ้อนลงไปลึกเกินไปและคืนค่าตั้งแต่ต้น (ภาค 1))
     * [หลีกเลี่ยงโค้ดที่ซ้อนลงไปลึกเกินไปและคืนค่าตั้งแต่ต้น (ภาค 2)](#หลีกเลี่ยงโค้ดที่ซ้อนลงไปลึกเกินไปและคืนค่าตั้งแต่ต้น (ภาค 2))
     * [หลีกเลี่ยงการต้องไล่ลำดับเอง](#หลีกเลี่ยงการต้องไล่ลำดับเอง)
     * [อย่าเพิ่มสิ่งที่ไม่จำเป็น](#อย่าเพิ่มสิ่งที่ไม่จำเป็น)
     * [ให้อาร์กิวเมนต์มีค่าเริ่มต้น แทนที่การใช้ทางลัดหรือใช้การเช็คเงื่อนไข](#ให้อาร์กิวเมนต์มีค่าเริ่มต้น-แทนที่การใช้ทางลัดหรือใช้การเช็คเงื่อนไข)
  3. [Comparison](#comparison)
     * [Use identical comparison](#use-identical-comparison)
  4. [ฟังก์ชัน](#ฟังก์ชัน)
     * [อาร์กิวเมนท์ในฟังก์ชัน (2 ตัวหรือน้อยกว่าจะดีมาก)](#อาร์กิวเมนท์ในฟังก์ชัน (2 ตัวหรือน้อยกว่าจะดีมาก))
     * [ฟังก์ชันควรจะทำงานเพียงอย่างเดียว](#ฟังก์ชันควรจะทำงานเพียงอย่างเดียว)
     * [ชื่อฟังก์ชันควรจะสื่อว่ามันทำอะไร](#ชื่อฟังก์ชันควรจะสื่อว่ามันทำอะไร)
     * [ฟังก์ชันควรจะมีสาระสำคัญแค่ระดับเดียว](#ฟังก์ชันควรจะมีสาระสำคัญแค่ระดับเดียว)
     * [อย่าใช้แฟล็ก (Flag) เป็นพารามิเตอร์ของฟังก์ชัน](#อย่าใช้แฟล็ก-(Flag)-เป็นพารามิเตอร์ของฟังก์ชัน)
     * [ระวังผลข้างเคียง (size effects)](#ระวังผลข้างเคียง (size effects))
     * [อย่าเขียนฟังก์ชันแบบโกลบอล](#อย่าเขียนฟังก์ชันแบบโกลบอล)
     * [อย่าใช้แพทเทิน ซิงเกิลตัน (Singleton)](#อย่าใช้แพทเทิน-ซิงเกิลตัน-(Singleton))
     * [ซ่อนการทำงานของเงื่อนไข](#ซ่อนการทำงานของเงื่อนไข)
     * [อย่าใช้เงื่อนไขที่เป็นเชิงลบ](#อย่าใช้เงื่อนไขที่เป็นเชิงลบ)
     * [เลิกใช้เงื่อนไขไปเลย](#เลิกใช้เงื่อนไขไปเลย)
     * [หลีกเลี่ยงการตรวจสอบชนิดข้อมูล (ภาค 1) ](#หลีกเลี่ยงการตรวจสอบชนิดข้อมูล (ภาค 1))
     * [หลีกเลี่ยงการตรวจสอบชนิดข้อมูล (ภาค 2) ](#หลีกเลี่ยงการตรวจสอบชนิดข้อมูล (ภาค 2))
     * [เอาโค้ดที่ตายแล้วออกไป](#เอาโค้ดที่ตายแล้วออกไป)
  5. [อ็อบเจคและโครงสร้างข้อมูล](#อ็อบเจคและโครงสร้างข้อมูล)
     * [ใช้การซ่อนเนื้อหาของอ็อบเจค (object encapsulation)](#ใช้การซ่อนเนื้อหาของอ็อบเจค (object encapsulation))
     * [Make objects have private/protected members](#make-objects-have-privateprotected-members)
  6. [คลาส](#classes)
     * [Prefer composition over inheritance](#prefer-composition-over-inheritance)
     * [Avoid fluent interfaces](#avoid-fluent-interfaces)
     * [Prefer `final` classes](#prefer-final-classes)
  7. [SOLID](#solid)
     * [Single Responsibility Principle (SRP)](#single-responsibility-principle-srp)
     * [Open/Closed Principle (OCP)](#openclosed-principle-ocp)
     * [Liskov Substitution Principle (LSP)](#liskov-substitution-principle-lsp)
     * [Interface Segregation Principle (ISP)](#interface-segregation-principle-isp)
     * [Dependency Inversion Principle (DIP)](#dependency-inversion-principle-dip)
  8. [Don’t repeat yourself (DRY)](#dont-repeat-yourself-dry)
  9. [การแปล](#translations)

## บทนำ

หลักการทางวิศวกรรมซอฟแวร์ จากหนังสือของโรเบิร์ต ซี. มาร์ติน เรื่อง
[*Clean Code*](https://www.amazon.com/Clean-Code-Handbook-Software-Craftsmanship/dp/0132350882),
โดยปรับตัวอย่างให้เป็นภาษา PHP เอกสารนี้ไม่ใช่แนวทางการเขียนโปรแกรมให้สวยงาม แต่มันเป็นแนวทางในการสร้างซอฟแวร์ด้วย PHP ที่อ่านง่าย นำกลับมาใช้ได้ และสามารถปรับปรุงได้

คุณไม่จำเป็นต้องยึดถือหลักการในเอกสารนี้อย่างเข้มงวดและไม่จำเป็นต้องเห็นด้วยในบางเรื่อง เนื้อหานี้เป็นเพียงแนวทางเท่านั้น หากแต่มันเป็นผลผลิตจากการเก็บเกี่ยวประสบการณ์หลายปีของผู้เขียนหนังสือ *Clean Code*

ได้รับแรงบันดาลใจจาก [clean-code-javascript](https://github.com/ryanmcdermott/clean-code-javascript)

ถึงแม้ว่านักพัฒนาส่วนใหญ่ยังใช้ PHP 5 แต่ตัวอย่างในบทความนี้ใช้ได้กับ PHP 7.1 หรือใหม่กว่าเท่านั้น

## **ตัวแปร**

### ใช้ชื่อตัวแปรที่มีความหมายและอ่านออกเสียงได้

**ไม่ดี:**

```php
$ymdstr = $moment->format('y-m-d');
```

**ดี:**

```php
$currentDate = $moment->format('y-m-d');
```

**[⬆ กลับไปด้านบน](#สารบัญ)**

### ใช้ศัพท์เดียวกันสำหรับตัวแปรชนิดเดียวกัน

**ไม่ดี:**

```php
getUserInfo();
getUserData();
getUserRecord();
getUserProfile();
```

**ดี:**

```php
getUser();
```

**[⬆ กลับไปด้านบน](#สารบัญ)**

### ใช้ชื่อที่ค้นหาเจอได้ (ภาค 1)

เราต้องอ่านโค้ดมากกว่าเขียน จึงจำเป็นที่โค้ดของเราต้องอ่านง่ายและหาสิ่งที่ต้องการได้ง่าย ตั้งชื่อตัวแปรที่เข้าใจยากมันทำร้ายคนอ่าน ใช้ชื่อที่ค้นหาได้

**ไม่ดี:**

```php
// 448 เอาไว้ทำอะไร?
$result = $serializer->serialize($data, 448);
```

**ดี:**

```php
$json = $serializer->serialize($data, JSON_UNESCAPED_SLASHES | JSON_PRETTY_PRINT | JSON_UNESCAPED_UNICODE);
```

### ใช้ชื่อที่ค้นหาเจอได้ (ภาค 2)

**ไม่ดี:**

```php
// 4 เอาไว้ทำอะไรเนี่ย?
if ($user->access & 4) {
    // ...
}
```

**ดี:**

```php
class User
{
    const ACCESS_READ = 1;
    const ACCESS_CREATE = 2;
    const ACCESS_UPDATE = 4;
    const ACCESS_DELETE = 8;
}

if ($user->access & User::ACCESS_UPDATE) {
    // do edit ...
}
```

**[⬆ กลับไปด้านบน](#สารบัญ)**


### ใช้ตัวแปรที่อธิบายตัวเองได้

**ไม่ดี:**

```php
$address = 'One Infinite Loop, Cupertino 95014';
$cityZipCodeRegex = '/^[^,]+,\s*(.+?)\s*(\d{5})$/';
preg_match($cityZipCodeRegex, $address, $matches);

saveCityZipCode($matches[1], $matches[2]);
```

**ไม่เลว:**:

ดีขึ้น แต่เรายังต้องพึ่งพา regex มากไป

```php
$address = 'One Infinite Loop, Cupertino 95014';
$cityZipCodeRegex = '/^[^,]+,\s*(.+?)\s*(\d{5})$/';
preg_match($cityZipCodeRegex, $address, $matches);

[, $city, $zipCode] = $matches;
saveCityZipCode($city, $zipCode);
```

**ดี:**:

ลดการพึ่งพา regex ด้วยการตั้งชื่อให้แพทเทินย่อย

```php
$address = 'One Infinite Loop, Cupertino 95014';
$cityZipCodeRegex = '/^[^,]+,\s*(?<city>.+?)\s*(?<zipCode>\d{5})$/';
preg_match($cityZipCodeRegex, $address, $matches);

saveCityZipCode($matches['city'], $matches['zipCode']);
```

**[⬆ กลับไปด้านบน](#สารบัญ)**

### หลีกเลี่ยงโค้ดที่ซ้อนลงไปลึกเกินไปและคืนค่าตั้งแต่ต้น (ภาค 1)

คำสั่ง if else มากเกินไปทำให้ไล่โค้ดได้ยาก ความเฉพาะเจาะจงดีกว่าต้องคาดเดา

**ไม่ดี:**

```php
function isShopOpen($day): bool
{
    if ($day) {
        if (is_string($day)) {
            $day = strtolower($day);
            if ($day === 'friday') {
                return true;
            } elseif ($day === 'saturday') {
                return true;
            } elseif ($day === 'sunday') {
                return true;
            } else {
                return false;
            }
        } else {
            return false;
        }
    } else {
        return false;
    }
}
```

**ดี:**

```php
function isShopOpen(string $day): bool
{
    if (empty($day)) {
        return false;
    }

    $openingDays = [
        'friday', 'saturday', 'sunday'
    ];

    return in_array(strtolower($day), $openingDays, true);
}
```

**[⬆ กลับไปด้านบน](#สารบัญ)**

### หลีกเลี่ยงโค้ดที่ซ้อนลงไปลึกเกินไปและคืนค่าตั้งแต่ต้น (ภาค 2)

**ไม่ดี:**

```php
function fibonacci(int $n)
{
    if ($n < 50) {
        if ($n !== 0) {
            if ($n !== 1) {
                return fibonacci($n - 1) + fibonacci($n - 2);
            } else {
                return 1;
            }
        } else {
            return 0;
        }
    } else {
        return 'Not supported';
    }
}
```

**ดี:**

```php
function fibonacci(int $n): int
{
    if ($n === 0 || $n === 1) {
        return $n;
    }

    if ($n > 50) {
        throw new \Exception('Not supported');
    }

    return fibonacci($n - 1) + fibonacci($n - 2);
}
```

**[⬆ กลับไปด้านบน](#สารบัญ)**

### หลีกเลี่ยงการต้องไล่ลำดับเอง
อย่าบังคับให้คนที่อ่านโค้ดคุณต้องไล่เรียงว่าตัวแปรนั้นหมายถึงอะไร ประกาศแบบเฉพาะเจาะจงดีกว่า

**ไม่ดี:**

```php
$l = ['Austin', 'New York', 'San Francisco'];

for ($i = 0; $i < count($l); $i++) {
    $li = $l[$i];
    doStuff();
    doSomeOtherStuff();
    // ...
    // ...
    // ...
    // Wait, what is `$li` for again?
    dispatch($li);
}
```

**ดี:**

```php
$locations = ['Austin', 'New York', 'San Francisco'];

foreach ($locations as $location) {
    doStuff();
    doSomeOtherStuff();
    // ...
    // ...
    // ...
    dispatch($location);
}
```

**[⬆ กลับไปด้านบน](#สารบัญ)**

### อย่าเพิ่มสิ่งที่ไม่จำเป็น

ถ้าชื่อคลาสหรือออบเจคบอกอะไรบางอย่างอยู่แล้ว อย่าใส่มันในชื่อตัวแปรภายในอีก

**ไม่ดี:**

```php
class Car
{
    public $carMake;
    public $carModel;
    public $carColor;

    //...
}
```

**ดี**:

```php
class Car
{
    public $make;
    public $model;
    public $color;

    //...
}
```

**[⬆ กลับไปด้านบน](#สารบัญ)**

### ให้อาร์กิวเมนต์มีค่าเริ่มต้น แทนที่การใช้ทางลัดหรือใช้การเช็คเงื่อนไข

**ไม่ดี:**

ไม่ดีเพราะ `$breweryName` สามารถเป็น `NULL`.

```php
function createMicrobrewery($breweryName = 'Hipster Brew Co.'): void
{
    // ...
}
```

**ไม่เลว:**

โค้ดชุดนี้เข้าใจได้ง่ายกว่าชุดที่แล้ว มีการตรวจสอบตัวแปร

```php
function createMicrobrewery($name = null): void
{
    $breweryName = $name ?: 'Hipster Brew Co.';
    // ...
}
```

**ดี:**

ถ้าคุณใช้ PHP 7+ คุณสามารถใช้ [type hinting](http://php.net/manual/en/functions.arguments.php#functions.arguments.type-declaration) และแน่ใจได้ว่า `$breweryName` จะไม่เป็น `NULL`.

```php
function createMicrobrewery(string $breweryName = 'Hipster Brew Co.'): void
{
    // ...
}
```

**[⬆ กลับไปด้านบน](#สารบัญ)**

## Comparison

### Use [identical comparison](http://php.net/manual/en/language.operators.comparison.php)

**Not good:**

The simple comparison will convert the string in an integer.

```php
$a = '42';
$b = 42;

if ($a != $b) {
   // The expression will always pass
}
```

The comparison `$a != $b` returns `FALSE` but in fact it's `TRUE`!
The string `42` is different than the integer `42`.

**Good:**

The identical comparison will compare type and value.

```php
$a = '42';
$b = 42;

if ($a !== $b) {
    // The expression is verified
}
```

The comparison `$a !== $b` returns `TRUE`.

**[⬆ back to top](#table-of-contents)**

## **ฟังก์ชัน**

### อาร์กิวเมนท์ในฟังก์ชัน (2 ตัวหรือน้อยกว่าจะดีมาก)

การจำกัดจำนวนพารามิเตอ์ในฟังก์ชันเป็นสิ่งที่สำคัญมาก เพราะจะทำให้ทดสอบฟังก์ชันนั้นได้ง่ายขึ้น 
หากมีมากกว่า 3 มักจะเพิ่มความยุ่งยากเพราะต้องทดสอบหลายเคสกับอาร์กิวเมนท์แต่ละตัว

ไม่มีอาร์กิวเมนท์เลยถือเป็นเคสอุดมคติ มีหนึ่งหรือสองตัวยังพอใช้ได้ และควรหลีกเลี่ยงการมีสามตัวหรือมากกว่า
โดยทั่วไปแล้วถ้ามีมากกว่า 2 ตัวแสดงว่าฟังก์ชันของคุณทำงานมากเกินไป ถ้าไม่ใช่นั้นส่วนใหญ่แล้วการใช้อ๊อบเจคมาเป็นอาร์กิวเมนท์เป็นสิ่งที่ดีกว่า

**ไม่ดี:**
```php
function createMenu(string $title, string $body, string $buttonText, bool $cancellable): void
{
    // ...
}
```

**ดี**:
```php
class MenuConfig
{
    public $title;
    public $body;
    public $buttonText;
    public $cancellable = false;
}

$config = new MenuConfig();
$config->title = 'Foo';
$config->body = 'Bar';
$config->buttonText = 'Baz';
$config->cancellable = true;

function createMenu(MenuConfig $config): void
{
    // ...
}
```

**[⬆ กลับไปด้านบน](#สารบัญ)**

### ฟังก์ชันควรจะทำงานเพียงอย่างเดียว

นี่เป็นกฏที่สำคัญมากกฏหนึ่งในวิศวกรรมซอฟแวร์เลยทีเดียว ถ้าฟังก์ชันทำงานมากกว่าหนึ่งอย่าง 
มันจะเขียนยาก ทดสอบยาก และเข้าใจความหมายได้ยาก เมื่อคุณแยกให้มันทำงานอย่างเดียว มันจะปรับปรุงได้ง่ายและโค้ดของคุณจะสะอาดขึ้น
ถ้าคุณยึดถือคำแนะนำนี้เป็นสำคัญ คุณจะนำหน้าเดเวลลอปเปอร์หลายคนทีเดียว

**ไม่ดี:**
```php
function emailClients(array $clients): void
{
    foreach ($clients as $client) {
        $clientRecord = $db->find($client);
        if ($clientRecord->isActive()) {
            email($client);
        }
    }
}
```

**ดี:**
```php
function emailClients(array $clients): void
{
    $activeClients = activeClients($clients);
    array_walk($activeClients, 'email');
}

function activeClients(array $clients): array
{
    return array_filter($clients, 'isClientActive');
}

function isClientActive(int $client): bool
{
    $clientRecord = $db->find($client);

    return $clientRecord->isActive();
}
```

**[⬆ กลับไปด้านบน](#สารบัญ)**

### ชื่อฟังก์ชันควรจะสื่อว่ามันทำอะไร

**ไม่ดี:**

```php
class Email
{
    //...

    public function handle(): void
    {
        mail($this->to, $this->subject, $this->body);
    }
}

$message = new Email(...);
// อะไรเนี่ย? จัดการข้อความ? นี่เรากำลังจะเขียนลงไฟล์เหรอ?
$message->handle();
```

**ดี:**

```php
class Email 
{
    //...

    public function send(): void
    {
        mail($this->to, $this->subject, $this->body);
    }
}

$message = new Email(...);
// เคลียร์และชัดเจน
$message->send();
```

**[⬆ กลับไปด้านบน](#สารบัญ)**

### ฟังก์ชันควรจะมีสาระสำคัญแค่ระดับเดียว

ถ้าคุณมีสาระสำคัญมากกว่าหนึ่งระดับ ฟังก์ชันของคุณมักจะทำงานมากเกินไป การแยกฟังก์ชันออกทำให้นำกลับมาใช้ใหม่ได้และทำให้ทดสอบง่ายขึ้น

**ไม่ดี:**

```php
function parseBetterJSAlternative(string $code): void
{
    $regexes = [
        // ...
    ];

    $statements = explode(' ', $code);
    $tokens = [];
    foreach ($regexes as $regex) {
        foreach ($statements as $statement) {
            // ...
        }
    }

    $ast = [];
    foreach ($tokens as $token) {
        // lex...
    }

    foreach ($ast as $node) {
        // parse...
    }
}
```

**นี่ก็ยังไม่ดี:**

เราแยกฟังก์ชันออกมา แต่ฟังก์ชัน `parseBetterJSAlternative()` ก็ยังซับซ้อนและยังทดสอบไม่ได้อยู่ดี

```php
function tokenize(string $code): array
{
    $regexes = [
        // ...
    ];

    $statements = explode(' ', $code);
    $tokens = [];
    foreach ($regexes as $regex) {
        foreach ($statements as $statement) {
            $tokens[] = /* ... */;
        }
    }

    return $tokens;
}

function lexer(array $tokens): array
{
    $ast = [];
    foreach ($tokens as $token) {
        $ast[] = /* ... */;
    }

    return $ast;
}

function parseBetterJSAlternative(string $code): void
{
    $tokens = tokenize($code);
    $ast = lexer($tokens);
    foreach ($ast as $node) {
        // parse...
    }
}
```

**ดี:**

ทางออกที่ดีที่สุดคือย้ายดีเพนเดนซี่ (dependencies) ของ `parseBetterJSAlternative()` ออกมาเพื่อให้ทดสอบได้

```php
class Tokenizer
{
    public function tokenize(string $code): array
    {
        $regexes = [
            // ...
        ];

        $statements = explode(' ', $code);
        $tokens = [];
        foreach ($regexes as $regex) {
            foreach ($statements as $statement) {
                $tokens[] = /* ... */;
            }
        }

        return $tokens;
    }
}

class Lexer
{
    public function lexify(array $tokens): array
    {
        $ast = [];
        foreach ($tokens as $token) {
            $ast[] = /* ... */;
        }

        return $ast;
    }
}

class BetterJSAlternative
{
    private $tokenizer;
    private $lexer;

    public function __construct(Tokenizer $tokenizer, Lexer $lexer)
    {
        $this->tokenizer = $tokenizer;
        $this->lexer = $lexer;
    }

    public function parse(string $code): void
    {
        $tokens = $this->tokenizer->tokenize($code);
        $ast = $this->lexer->lexify($tokens);
        foreach ($ast as $node) {
            // parse...
        }
    }
}
```

**[⬆ กลับไปด้านบน](#สารบัญ)**

### อย่าใช้แฟล็ก (Flag) เป็นพารามิเตอร์ของฟังก์ชัน

แฟล็กเป็นตัวบอกผู้ใช้ของคุณว่าฟังก์ชันนี้ทำงานมากกว่าหนึ่งอย่าง ฟังก์ชันควรทำงานอย่างเดียว ให้แยกฟังก์ชันออกไป
ถ้ามันต้องทำงานแยกเส้นทางไปตามค่าของบูลีน (boolean: True - False)

**ไม่ดี:**

```php
function createFile(string $name, bool $temp = false): void
{
    if ($temp) {
        touch('./temp/'.$name);
    } else {
        touch($name);
    }
}
```

**ดี**:

```php
function createFile(string $name): void
{
    touch($name);
}

function createTempFile(string $name): void
{
    touch('./temp/'.$name);
}
```

**[⬆ กลับไปด้านบน](#สารบัญ)**

### ระวังผลข้างเคียง (size effects)

ฟังก์ชันจะทำให้เกิดผลข้างเคียงหากมันทำอะไรมากกว่าการรับค่าเข้ามาและคืนค่าออกไป ผลข้างเคียงอย่างเช่นเขียนลงไฟล์
แก้ไขตัวแปรระดับโกลบอล หรือโอนเงินของคุณไปให้คนแปลกหน้าโดยไม่ได้ตั้งใจ

เอาหละ บางทีคุณอาจจะต้องการผลข้างเคียงนั่นจริง ๆ อย่างในตัวอย่างข้างต้น คุณอาจต้องการที่จะเขียนลงไฟล์ สิ่งที่คุณต้องทำคือจับมันไปรวมไว้ส่วนกลาง อย่ามีฟังก์ชันหรือคลาสหลายตัวที่เขียนไฟล์ ให้มีเซอร์วิสเดียวที่ทำ ตัวเดียวเลย

เหตุผลหลักคือการหลีกเลี่ยงข้อผิดพลาดที่เจอบ่อย เช่น การแชร์สถานะ (state) ระหว่างอ๊อบเจคโดยที่ไม่มีโครงสร้างอะไรรองรับ การใช้ชนิตข้อมูลที่เปลี่ยนแปลงได้ (mutable data types) ที่มักจะถูกทำให้เปลี่ยนแปลงไปโดยโค้ดส่วนไหนก็ได้ และการไม่มีส่วนกลางมาควบคุมผลข้างเคียง ถ้าคุณจัดการเรื่องเหล่านี้ได้ คุณจะมีความสุขมากกว่าโปรแกรมเมอร์ส่วนใหญ่ทั่วโลกเลยทีเดียว

**ไม่ดี:**

```php
// ตัวแปรระดับโกลบอล เรียกใช้แบบ reference ด้วยฟังก์ชันนี้
// ถ้าเรามีฟังก์ชันที่ใช้ตัวแปรชื่อนี้เหมือนกัน ที่นีกลายเป็น array ไปแล้ว และจะเกิดข้อผิดพลาดได้

$name = 'Ryan McDermott';

function splitIntoFirstAndLastName(): void
{
    global $name;

    $name = explode(' ', $name);
}

splitIntoFirstAndLastName();

var_dump($name); // ['Ryan', 'McDermott'];
```

**ดี:**

```php
function splitIntoFirstAndLastName(string $name): array
{
    return explode(' ', $name);
}

$name = 'Ryan McDermott';
$newName = splitIntoFirstAndLastName($name);

var_dump($name); // 'Ryan McDermott';
var_dump($newName); // ['Ryan', 'McDermott'];
```

**[⬆ กลับไปด้านบน](#สารบัญ)**

### อย่าเขียนฟังก์ชันแบบโกลบอล

การทำให้ระดับโกลบอลมีมลพิษถือเป็นสิ่งที่ต้องหลีกเลี่ยงในหลาย ๆ ภาษา เพราะคุณอาจจะไปชนกับไลบรารี่อื่นและผู้ใช้งาน API ของคุณอาจจะไม่รู้มาก่อนจนกระทั้งไปเจอข้อผิดพลาดในระยะโปรดักชัน ลองคิดตามตัวอย่างนี้ จะเป็นอย่างไรถ้าคุณต้องการค่าคอนฟิกกุเรชันที่เป็นอาร์เรย์ คุณอาจจะเขียนฟังก์ชันแบบโกลบอลเช่น `config()` แต่มันไปชนกับฟังก์ชันที่อยู่ในไลบรารี่อื่นที่พยายามจะทำสิ่งเดียวกัน


**ไม่ดี:**

```php
function config(): array
{
    return  [
        'foo' => 'bar',
    ]
}
```

**ดี:**

```php
class Configuration
{
    private $configuration = [];

    public function __construct(array $configuration)
    {
        $this->configuration = $configuration;
    }

    public function get(string $key): ?string
    {
        return isset($this->configuration[$key]) ? $this->configuration[$key] : null;
    }
}
```

โหลดคอนฟิกกุเรชันและสร้างอินสแตนส์ของคลาส `Configuration`

```php
$configuration = new Configuration([
    'foo' => 'bar',
]);
```

และต่อจากนี้คุณต้องใช้อินสแตนส์ของ `Configuration` นี้ในโปรแกรมของคุณทั้งหมด

**[⬆ กลับไปด้านบน](#สารบัญ)**

### อย่าใช้แพทเทิน ซิงเกิลตัน (Singleton)

ซิงเกิลตันเป็น [แอนติ-แพทเทิน](https://en.wikipedia.org/wiki/Singleton_pattern). ถอดความจาก Brian Button:
 1. มันมักจะถูกใช้เป็น **อินแสตนส์แบบโกลบอล** ทำไมมันถึงได้แย่นัก เพราะคุณ **ซ่อนดีเพนเดนซี่ (Dependencies)** ของโปรแกรมคุณแทนที่จะเปิดเผยมันผ่านอินเตอร์เฟส การจัดบางสิ่งให้อยู่ระดับโกลบอลเพื่อเลี่ยงการส่งผ่านมันไปมาถือว่าเป็น [code smell](https://en.wikipedia.org/wiki/Code_smell).
 2. มันเป็นการละเมิด [หลักการความรับผิดชอบเดียว (single responsibility principle)](#single-responsibility-principle-srp): จากข้อเท็จจริงที่ว่า **มันควบคุมการสร้างตัวเองและวงจรชีวิต (they control their own creation and lifecycle)**.
 3. มันทำให้เกิดโค้ดที่ยึดโยงกัน [coupled](https://en.wikipedia.org/wiki/Coupling_%28computer_programming%29). ทำการการทดสอบด้วยการเฟคทำได้ยากในหลายกรณี
 4. มันแบกสถานะไปด้วยตลอดอายุการทำงานของแอพลิเคชัน เป็นการขัดขวางการทดสอบอีกอย่าง ทำให้ต้องทดสอบแบบเป็นลำดับขั้น ซึ่งไม่ดีเลยกับการทำยูนิตเทส ทำไมเหรอ เพราะยูนิตเทสควรจะเป็นอิสระต่อกันไง

อันนี้เป็นความคิดเห็นที่ดีโดย [Misko Hevery](http://misko.hevery.com/about/) เกี่ยวกับ [ต้นตอของปัญหา (root of problem)](http://misko.hevery.com/2008/08/25/root-cause-of-singletons/).

**ไม่ดี:**

```php
class DBConnection
{
    private static $instance;

    private function __construct(string $dsn)
    {
        // ...
    }

    public static function getInstance(): DBConnection
    {
        if (self::$instance === null) {
            self::$instance = new self();
        }

        return self::$instance;
    }

    // ...
}

$singleton = DBConnection::getInstance();
```

**ดี:**

```php
class DBConnection
{
    public function __construct(string $dsn)
    {
        // ...
    }

     // ...
}
```

สร้างอินสแตนส์ของคลาส `DBConnection` และคอนฟิกมันด้วย [DSN](http://php.net/manual/en/pdo.construct.php#refsect1-pdo.construct-parameters).

```php
$connection = new DBConnection($dsn);
```

และคุณควรใช้อินสแตนส์ของ `DBConnection` ตลอดทั้งแอพลิเคชัน

**[⬆ กลับไปด้านบน](#สารบัญ)**

### ซ่อนการทำงานของเงื่อนไข

**ไม่ดี:**

```php
if ($article->state === 'published') {
    // ...
}
```

**ดี:**

```php
if ($article->isPublished()) {
    // ...
}
```

**[⬆ กลับไปด้านบน](#สารบัญ)**

### อย่าใช้เงื่อนไขที่เป็นเชิงลบ

**ไม่ดี:**

```php
function isDOMNodeNotPresent(\DOMNode $node): bool
{
    // ...
}

if (!isDOMNodeNotPresent($node))
{
    // ...
}
```

**ดี:**

```php
function isDOMNodePresent(\DOMNode $node): bool
{
    // ...
}

if (isDOMNodePresent($node)) {
    // ...
}
```

**[⬆ กลับไปด้านบน](#สารบัญ)**

### เลิกใช้เงื่อนไขไปเลย

มันดูเป็นเรื่องเหนือจริงไปหน่อย ถ้าได้ยินครั้งแรกส่วนใหญ่จะพูดขึ้นว่า "จะทำงานอะไรได้ยังไงถ้าไม่มี `if`?" 
คำตอบคือคุณสามารถใช้หลักการโพลีมอฟิสมาแทนได้ในหลาย ๆ กรณี คำถามต่อมาคือ "อืม ก็ฟังดูดีนะ แต่ทำไมฉันต้องทำงั้นด้วยล่ะ?"
คำตอบก็คือแนวคิดคลีนโค้ดที่เราเรียนผ่านมาแล้ว นั่นคือ ฟังก์ชันควรทำงานอย่างเดียว เมื่อคุณมีคลาสและฟังก์ชันที่มี `if` แสดงว่าคุณกำลังบอกผู้ใช้ว่าฟังก์ชันของคุณกำลังทำงานมากกว่าอย่างเดียว จำได้มั๊ย? เพราะงั้นทำอย่างเดียวพอ

**ไม่ดี:**

```php
class Airplane
{
    // ...

    public function getCruisingAltitude(): int
    {
        switch ($this->type) {
            case '777':
                return $this->getMaxAltitude() - $this->getPassengerCount();
            case 'Air Force One':
                return $this->getMaxAltitude();
            case 'Cessna':
                return $this->getMaxAltitude() - $this->getFuelExpenditure();
        }
    }
}
```

**ดี:**

```php
interface Airplane
{
    // ...

    public function getCruisingAltitude(): int;
}

class Boeing777 implements Airplane
{
    // ...

    public function getCruisingAltitude(): int
    {
        return $this->getMaxAltitude() - $this->getPassengerCount();
    }
}

class AirForceOne implements Airplane
{
    // ...

    public function getCruisingAltitude(): int
    {
        return $this->getMaxAltitude();
    }
}

class Cessna implements Airplane
{
    // ...

    public function getCruisingAltitude(): int
    {
        return $this->getMaxAltitude() - $this->getFuelExpenditure();
    }
}
```

**[⬆ กลับไปด้านบน](#สารบัญ)**

### หลีกเลี่ยงการตรวจสอบชนิดข้อมูล (ภาค 1) 

PHP เป็นภาษาที่ไม่จำเป็นต้องประกาศชนิตของตัวแปร ซึ่งหมายความว่าฟังก์ชันของคุณสามารถรับอาร์กิวเมนท์เป็นอะไรก็ได้ บางทีก็โดนความเสรีนี้แว้งกัดบ่อย ๆ และมันก็ยั่วใจเหลือเกินที่จะทำการตรวจสอบชนิดข้อมูลก่อนทำงานในฟังก์ชัน มีหลายวิธีที่จะหลีกเลี่ยงได้ 
อย่างแรกที่ควรพิจารณาคือความสอดคล้องของ API*

**ไม่ดี:**

```php
function travelToTexas($vehicle): void
{
    if ($vehicle instanceof Bicycle) {
        $vehicle->pedalTo(new Location('texas'));
    } elseif ($vehicle instanceof Car) {
        $vehicle->driveTo(new Location('texas'));
    }
}
```

**ดี:**

```php
function travelToTexas(Traveler $vehicle): void
{
    $vehicle->travelTo(new Location('texas'));
}
```

*ผู้แปล: กรณีนี้คือการใช้ Type Hinting ใน PHP 5 หรือ Type Declaration ใน PHP 7 ถ้าตัวแปรที่ส่งเข้าฟังก์ชันไม่ใช่ชนิดข้อมูลที่ระบุก็จะฟ้องข้อผิดพลาดออกมา

**[⬆ กลับไปด้านบน](#สารบัญ)**

### หลีกเลี่ยงการตรวจสอบชนิดข้อมูล (ภาค 2) 

ถ้าคุณทำงานกับชนิดตัวแปรพื้นฐานอย่าง สตริง อินทิเจอ (integer) หรืออาร์เรย์
และคุณใช้ PHP 7+ และคุณไม่สามารถใช้โพลีมอฟิสได้ แต่คุณยังรู้สึกว่าต้องทำการตรวจสอบชนิดข้อมูลอยู่ดี คุณควรพิจารณาเรื่อง [type declaration](http://php.net/manual/en/functions.arguments.php#functions.arguments.type-declaration) หรือ โหมดเข้มงวด (strict mode) มันจะกำหนดให้คุณต้องประกาศตัวแปรพร้อมระบุชนิดข้อมูลด้วย
ปัญหาของการตรวจสอบชนิดข้อมูลด้วยตนเองคือมันต้องเพิ่มโค้ดจำนวนมากเข้าไปเพื่อให้แน่ใจว่าได้ชนิดข้อมูลที่ถูกต้อง ซึ่งไม่คุ้มกับที่ต้องเสียโค้ดที่อ่านง่ายไป พยายามให้โค้ดสะอาด เขียนเทสดี ๆ และมีการรีวิวโค้ดอย่างมีประสิทธิภาพ หรือไม่อย่างนั้นก็ทำทุกอย่างและใช้การกำหนดชนิดข้อมูลหรือใช้โหมดเข้มงวด

**ไม่ดี:**

```php
function combine($val1, $val2): int
{
    if (!is_numeric($val1) || !is_numeric($val2)) {
        throw new \Exception('Must be of type Number');
    }

    return $val1 + $val2;
}
```

**ดี:**

```php
function combine(int $val1, int $val2): int
{
    return $val1 + $val2;
}
```

**[⬆ กลับไปด้านบน](#สารบัญ)**

### เอาโค้ดที่ตายแล้วออกไป

โค้ดที่ไม่ได้ใช้แล้วก็ไม่ดีพอ ๆ กับโค้ดที่ซ้ำ ไม่มีเหตุผลอะไรจะเก็บไว้ในงาน ถ้ามันไม่ได้ถูกใช้ก็เอาออกไปเลย ยังไงมันก็ยังอยู่ในระบบเก็บเวอร์ชัน (version control system) อยู่ดีเมื่อคุณต้องการ

**ไม่ดี:**

```php
function oldRequestModule(string $url): void
{
    // ...
}

function newRequestModule(string $url): void
{
    // ...
}

$request = newRequestModule($requestUrl);
inventoryTracker('apples', $request, 'www.inventory-awesome.io');
```

**ดี:**

```php
function requestModule(string $url): void
{
    // ...
}

$request = requestModule($requestUrl);
inventoryTracker('apples', $request, 'www.inventory-awesome.io');
```

**[⬆ กลับไปด้านบน](#สารบัญ)**


## อ็อบเจคและโครงสร้างข้อมูล

### ใช้การซ่อนเนื้อหาของอ็อบเจค (object encapsulation)

ใน PHP คุณสามารถใช้คีย์เวิร์ด `public`, `protected` และ `private` กับเมทธอด
ใช้มันซะ คุณจะได้ควบคุมการเปลี่ยนแปลงพร็อบเพอตีของอ็อบเจคได้ 

* เมื่อคุณต้องการจะทำอะไรมากกว่าดึงข้อมูลพร็อบเพอตี คุณจะไม่ต้องค้นหาและเปลี่ยน
แอกเซสเซอร์ (accessor) ทุกตัวในโค้ดเบส
* ทำให้เพิ่มการตรวจสอบได้ง่ายเมื่อต้องใช้ `set`
* ซ่อนเนื้อหาไว้ภายใน
* ง่ายที่จะเพิ่มการทำบันทึก (logging) และการจัดการข้อผิดพลาดเมื่อทำการดึงและเปลี่ยนข้อมูล
* เมื่อสืบทอดคลาสนี้ คุณสามารถจะเปลี่ยนการทำงานจากแบบเดิมได้
* คุณสามารถทำเลซี่โหลด (lazy load) พร็อบเพอตีของอ็อบเจคของคุณได้ เช่นโหลดจาก server

ยิ่งกว่านั้น อันนี้เป็นส่วนหนึ่งของหลักการ โอเพน-โคลส (Open/Closed principle)

**ไม่ดี:**

```php
class BankAccount
{
    public $balance = 1000;
}

$bankAccount = new BankAccount();

// ซื้อรองเท้า...
$bankAccount->balance -= 100;
```

**ดี:**

```php
class BankAccount
{
    private $balance;

    public function __construct(int $balance = 1000)
    {
      $this->balance = $balance;
    }

    public function withdraw(int $amount): void
    {
        if ($amount > $this->balance) {
            throw new \Exception('Amount greater than available balance.');
        }

        $this->balance -= $amount;
    }

    public function deposit(int $amount): void
    {
        $this->balance += $amount;
    }

    public function getBalance(): int
    {
        return $this->balance;
    }
}

$bankAccount = new BankAccount();

// ซื้อรองเท้า ...
$bankAccount->withdraw($shoesPrice);

// เช็คยอด
$balance = $bankAccount->getBalance();
```

**[⬆ กลับไปด้านบน](#สารบัญ)**

### ให้อ็อบเจคมีองค์ประกอบแบบไพรเวทและโปรเทค

* เมดธอดและพร็อบเพอตีที่เป็น `public` เสี่ยงต่อการถูกเปลี่ยนแปลงมาก เพราะโค้ดอื่นบางตัวอาจจะมาอิงอยู่กับพวกมัน และคุณไม่สามารถควบคุมได้ว่าโค้ดส่วนไหนที่ถูกยึดโยงอยู่ **การเปลี่ยนแปลงใด ๆ ในคลาสจะทำให้เกิดอันตรายกับผู้ใช้คลาสทั้งหมด**
* โมดิฟายเออร์ `protected` ก็อันตรายไม่แพ้ public เพราะมันถูกเข้าถึงได้จากคลาสลูกคลาสไหนก็ได้ นั่นหมายความว่าสิ่งที่แตกต่างระหว่าง public กับ protected ก็แค่วิธีการเข้าถึงเท่านั้นเอง แต่การเอนแคปซูเลชั่นจะรับประกันว่าทุกอย่างจะเหมือนเดิม **การเปลี่ยนแปลงใด ๆ ในคลาสจะทำให้เกิดอันตรายกับคลาสลูกทั้งหมด**
* โมดิฟายเออร์ `private` รับประกันว่าโค้ดนั้น **ความเสี่ยงในการเปลี่ยนแปลงโค้ดจะถูกจำกัดอยู่ในคลาสเดียวเท่านั้น** (คุณจะปลอดภัยที่จะเปลี่ยนอะไรก็ได้และไม่ต้องเจอกับ [เจงก้า เอฟเฟค (Jenga effect)](http://www.urbandictionary.com/define.php?term=Jengaphobia&defid=2494196))

เพราะฉะนั้น ใช้ `private` เป็นค่าเริ่มต้น และใช้ `public/protected` เมื่อคุณต้องการให้คลาสอื่นเข้าถึงได้

คุณสามารถอ่านข้อมูลเพิ่มเติมได้จาก [บล็อกโพสนี้](http://fabien.potencier.org/pragmatism-over-theory-protected-vs-private.html) เขียนโดย [Fabien Potencier](https://github.com/fabpot)

**ไม่ดี:**

```php
class Employee
{
    public $name;

    public function __construct(string $name)
    {
        $this->name = $name;
    }
}

$employee = new Employee('John Doe');
echo 'Employee name: '.$employee->name; // Employee name: John Doe
```

**ดี:**

```php
class Employee
{
    private $name;

    public function __construct(string $name)
    {
        $this->name = $name;
    }

    public function getName(): string
    {
        return $this->name;
    }
}

$employee = new Employee('John Doe');
echo 'Employee name: '.$employee->getName(); // Employee name: John Doe
```

**[⬆ กลับไปด้านบน](#สารบัญ)**

## คลาส

### แนะนำให้ใช้การประกอบมากกว่าการสืบทอด (composition over inheritance)

อย่างที่กล่าวถึงใน [*Design Patterns*](https://en.wikipedia.org/wiki/Design_Patterns) โดยแก็งสี่สหาย (Gang of Four)
คุณควรจะใช้การประกอบมากกว่าการสืบทอดคลาสในจุดที่ทำได้ มีเหตุผลดี ๆ มากมายที่จะใช้การสืบทอดคลาส 
และมันก็มีเหตุผลอีกมากมายเหมือนกันที่จะใช้การประกอบ จุดหลักของคำกล่าวนี้คือถ้าใจคุณมุ่งไปที่การสืบทอด พยายาม
ลองคิดว่าการประกอบจะแก้ปัญหาให้คุณได้ดีกว่า ซึ่งในบางกรณีมันเป็นเช่นนั้น

คุณอาจจะกำลังคิดว่าแล้วเมื่อไรฉันถึงควรจะใช้การสืบทอดล่ะ? มันขึ้นอยู่กับปัญหาที่คุณเจอ
แต่ปัญหาเหล่านั้นมันก็มีไม่กี่อย่างที่การสืบทอดจะดูมีเหตุผลกว่าการประกอบ

1. การสืบทอดนั้นแสดงถึงความสัมพันธ์แบบการ "เป็นสิ่งหนึ่ง" และไม่ได้เป็นแบบ "มีสิ่งหนึ่ง" (คน -> สัตว์ กับ ผู้ใช้ -> รายละเอียดผู้ใช้)
2. คุณสามารถใช้โค้ดเก่าจากคลาสแม่ (คนสามารถเคลื่อนที่ได้เหมือนสัตว์ทั่วไป)
3. คุณต้องการจะให้เกิดการเปลี่ยนแปลงระดับโกลบอลโดยการเปลี่ยนที่คลาสแม่ (เปลี่ยนอัตราการเผาผลาญแคลอรี่ของสัตว์เมื่อเคลื่อนที่)

**ไม่ดี:**

```php
class Employee 
{
    private $name;
    private $email;

    public function __construct(string $name, string $email)
    {
        $this->name = $name;
        $this->email = $email;
    }

    // ...
}

// ไม่ดี เพราะ Employee "มี" ข้อมูลการเสียภาษี
// Employee TaxData ไม่ได้เป็น Employee

class EmployeeTaxData extends Employee 
{
    private $ssn;
    private $salary;
    
    public function __construct(string $name, string $email, string $ssn, string $salary)
    {
        parent::__construct($name, $email);

        $this->ssn = $ssn;
        $this->salary = $salary;
    }

    // ...
}
```

**ดี:**

```php
class EmployeeTaxData 
{
    private $ssn;
    private $salary;

    public function __construct(string $ssn, string $salary)
    {
        $this->ssn = $ssn;
        $this->salary = $salary;
    }

    // ...
}

class Employee 
{
    private $name;
    private $email;
    private $taxData;

    public function __construct(string $name, string $email)
    {
        $this->name = $name;
        $this->email = $email;
    }

    public function setTaxData(string $ssn, string $salary)
    {
        $this->taxData = new EmployeeTaxData($ssn, $salary);
    }

    // ...
}
```

**[⬆ กลับไปด้านบน](#สารบัญ)**

### Avoid fluent interfaces หลีกเลี่ยงฟลูเอนท์ อินเตอร์เฟส

[ฟลูเอนท์ อินเตอร์เฟส](https://en.wikipedia.org/wiki/Fluent_interface) 
เป็นลักษณะการโปรแกรมที่มีเป้าหมายเพื่อให้ซอสโค้ดอ่านได้ง่ายโดย [การเรียกเมธอดเป็นลูกโซ่](https://en.wikipedia.org/wiki/Method_chaining)

ข้อดีของมันคือในบางกรณีแพทเทินนี้จะลดรูปของโค้ดลง ตัวอย่างเช่น [PHPUnit Mock Builder](https://phpunit.de/manual/current/en/test-doubles.html)
หรือกับ [Doctrine Query Builder](http://docs.doctrine-project.org/projects/doctrine-dbal/en/latest/reference/query-builder.html)) แต่บ่อยครั้งที่มันมีต้นทุนสูง

1. ละเมิด [Encapsulation](https://en.wikipedia.org/wiki/Encapsulation_%28object-oriented_programming%29)
2. ละเมิด [Decorators](https://en.wikipedia.org/wiki/Decorator_pattern)
3. ทดสอบแบบ [mock](https://en.wikipedia.org/wiki/Mock_object) ได้ยาก 
4. ทำให้อ่านสิ่งที่เปลี่ยนแปลง (diffs) ในโค้ดได้ยาก

คุณสามารถอ่านข้อมูลเพิ่มเติมในเรื่องนี้ได้จาก [บล็อกโพส](https://ocramius.github.io/blog/fluent-interfaces-are-evil/) เขียนโดย [Marco Pivetta](https://github.com/Ocramius)

**ไม่ดี:**

```php
class Car
{
    private $make = 'Honda';
    private $model = 'Accord';
    private $color = 'white';

    public function setMake(string $make): self
    {
        $this->make = $make;

        // NOTE: Returning this for chaining
        return $this;
    }

    public function setModel(string $model): self
    {
        $this->model = $model;

        // NOTE: Returning this for chaining
        return $this;
    }

    public function setColor(string $color): self
    {
        $this->color = $color;

        // NOTE: Returning this for chaining
        return $this;
    }

    public function dump(): void
    {
        var_dump($this->make, $this->model, $this->color);
    }
}

$car = (new Car())
  ->setColor('pink')
  ->setMake('Ford')
  ->setModel('F-150')
  ->dump();
```

**ดี:**

```php
class Car
{
    private $make = 'Honda';
    private $model = 'Accord';
    private $color = 'white';

    public function setMake(string $make): void
    {
        $this->make = $make;
    }

    public function setModel(string $model): void
    {
        $this->model = $model;
    }

    public function setColor(string $color): void
    {
        $this->color = $color;
    }

    public function dump(): void
    {
        var_dump($this->make, $this->model, $this->color);
    }
}

$car = new Car();
$car->setColor('pink');
$car->setMake('Ford');
$car->setModel('F-150');
$car->dump();
```

**[⬆ กลับไปด้านบน](#สารบัญ)**

### Prefer final classes

The `final` should be used whenever possible:

1. It prevents uncontrolled inheritance chain.
2. It encourages [composition](#prefer-composition-over-inheritance).
3. It encourages the [Single Responsibility Pattern](#single-responsibility-principle-srp).
4. It encourages developers to use your public methods instead of extending the class to get access on protected ones.
5. It allows you to change your code without any break of applications that use your class.

The only condition is that your class should implement an interface and no other public methods are defined.

For more informations you can read [the blog post](https://ocramius.github.io/blog/when-to-declare-classes-final/) on this topic written by [Marco Pivetta (Ocramius)](https://ocramius.github.io/).

**Bad:**

```php
final class Car
{
    private $color;
    
    public function __construct($color)
    {
        $this->color = $color;
    }
    
    /**
     * @return string The color of the vehicle
     */
    public function getColor() 
    {
        return $this->color;
    }
}
```

**Good:**

```php
interface Vehicle
{
    /**
     * @return string The color of the vehicle
     */
    public function getColor();
}

final class Car implements Vehicle
{
    private $color;
    
    public function __construct($color)
    {
        $this->color = $color;
    }
    
    /**
     * {@inheritdoc}
     */
    public function getColor() 
    {
        return $this->color;
    }
}
```

**[⬆ back to top](#table-of-contents)**

## SOLID

**SOLID** is the mnemonic acronym introduced by Michael Feathers for the first five principles named by Robert Martin, which meant five basic principles of object-oriented programming and design.

 * [S: Single Responsibility Principle (SRP)](#single-responsibility-principle-srp)
 * [O: Open/Closed Principle (OCP)](#openclosed-principle-ocp)
 * [L: Liskov Substitution Principle (LSP)](#liskov-substitution-principle-lsp)
 * [I: Interface Segregation Principle (ISP)](#interface-segregation-principle-isp)
 * [D: Dependency Inversion Principle (DIP)](#dependency-inversion-principle-dip)

### Single Responsibility Principle (SRP)

As stated in Clean Code, "There should never be more than one reason for a class
to change". It's tempting to jam-pack a class with a lot of functionality, like
when you can only take one suitcase on your flight. The issue with this is
that your class won't be conceptually cohesive and it will give it many reasons
to change. Minimizing the amount of times you need to change a class is important.
It's important because if too much functionality is in one class and you modify a piece of it,
it can be difficult to understand how that will affect other dependent modules in
your codebase.

**Bad:**

```php
class UserSettings
{
    private $user;

    public function __construct(User $user)
    {
        $this->user = $user;
    }

    public function changeSettings(array $settings): void
    {
        if ($this->verifyCredentials()) {
            // ...
        }
    }

    private function verifyCredentials(): bool
    {
        // ...
    }
}
```

**Good:**

```php
class UserAuth 
{
    private $user;

    public function __construct(User $user)
    {
        $this->user = $user;
    }
    
    public function verifyCredentials(): bool
    {
        // ...
    }
}

class UserSettings 
{
    private $user;
    private $auth;

    public function __construct(User $user) 
    {
        $this->user = $user;
        $this->auth = new UserAuth($user);
    }

    public function changeSettings(array $settings): void
    {
        if ($this->auth->verifyCredentials()) {
            // ...
        }
    }
}
```

**[⬆ กลับไปด้านบน](#สารบัญ)**

### Open/Closed Principle (OCP)

As stated by Bertrand Meyer, "software entities (classes, modules, functions,
etc.) should be open for extension, but closed for modification." What does that
mean though? This principle basically states that you should allow users to
add new functionalities without changing existing code.

**Bad:**

```php
abstract class Adapter
{
    protected $name;

    public function getName(): string
    {
        return $this->name;
    }
}

class AjaxAdapter extends Adapter
{
    public function __construct()
    {
        parent::__construct();

        $this->name = 'ajaxAdapter';
    }
}

class NodeAdapter extends Adapter
{
    public function __construct()
    {
        parent::__construct();

        $this->name = 'nodeAdapter';
    }
}

class HttpRequester
{
    private $adapter;

    public function __construct(Adapter $adapter)
    {
        $this->adapter = $adapter;
    }

    public function fetch(string $url): Promise
    {
        $adapterName = $this->adapter->getName();

        if ($adapterName === 'ajaxAdapter') {
            return $this->makeAjaxCall($url);
        } elseif ($adapterName === 'httpNodeAdapter') {
            return $this->makeHttpCall($url);
        }
    }

    private function makeAjaxCall(string $url): Promise
    {
        // request and return promise
    }

    private function makeHttpCall(string $url): Promise
    {
        // request and return promise
    }
}
```

**Good:**

```php
interface Adapter
{
    public function request(string $url): Promise;
}

class AjaxAdapter implements Adapter
{
    public function request(string $url): Promise
    {
        // request and return promise
    }
}

class NodeAdapter implements Adapter
{
    public function request(string $url): Promise
    {
        // request and return promise
    }
}

class HttpRequester
{
    private $adapter;

    public function __construct(Adapter $adapter)
    {
        $this->adapter = $adapter;
    }

    public function fetch(string $url): Promise
    {
        return $this->adapter->request($url);
    }
}
```

**[⬆ กลับไปด้านบน](#สารบัญ)**

### Liskov Substitution Principle (LSP)

This is a scary term for a very simple concept. It's formally defined as "If S
is a subtype of T, then objects of type T may be replaced with objects of type S
(i.e., objects of type S may substitute objects of type T) without altering any
of the desirable properties of that program (correctness, task performed,
etc.)." That's an even scarier definition.

The best explanation for this is if you have a parent class and a child class,
then the base class and child class can be used interchangeably without getting
incorrect results. This might still be confusing, so let's take a look at the
classic Square-Rectangle example. Mathematically, a square is a rectangle, but
if you model it using the "is-a" relationship via inheritance, you quickly
get into trouble.

**Bad:**

```php
class Rectangle
{
    protected $width = 0;
    protected $height = 0;

    public function setWidth(int $width): void
    {
        $this->width = $width;
    }

    public function setHeight(int $height): void
    {
        $this->height = $height;
    }

    public function getArea(): int
    {
        return $this->width * $this->height;
    }
}

class Square extends Rectangle
{
    public function setWidth(int $width): void
    {
        $this->width = $this->height = $width;
    }

    public function setHeight(int $height): void
    {
        $this->width = $this->height = $height;
    }
}

function printArea(Rectangle $rectangle): void
{
    $rectangle->setWidth(4);
    $rectangle->setHeight(5);
 
    // BAD: Will return 25 for Square. Should be 20.
    echo sprintf('%s has area %d.', get_class($rectangle), $rectangle->getArea()).PHP_EOL;
}

$rectangles = [new Rectangle(), new Square()];

foreach ($rectangles as $rectangle) {
    printArea($rectangle);
}
```

**Good:**

The best way is separate the quadrangles and allocation of a more general subtype for both shapes.

Despite the apparent similarity of the square and the rectangle, they are different.
A square has much in common with a rhombus, and a rectangle with a parallelogram, but they are not subtype.
A square, a rectangle, a rhombus and a parallelogram are separate shapes with their own properties, albeit similar.

```php
interface Shape
{
    public function getArea(): int;
}

class Rectangle implements Shape
{
    private $width = 0;
    private $height = 0;

    public function __construct(int $width, int $height)
    {
        $this->width = $width;
        $this->height = $height;
    }

    public function getArea(): int
    {
        return $this->width * $this->height;
    }
}

class Square implements Shape
{
    private $length = 0;

    public function __construct(int $length)
    {
        $this->length = $length;
    }

    public function getArea(): int
    {
        return $this->length ** 2;
    }
}

function printArea(Shape $shape): void
{
    echo sprintf('%s has area %d.', get_class($shape), $shape->getArea()).PHP_EOL;
}

$shapes = [new Rectangle(4, 5), new Square(5)];

foreach ($shapes as $shape) {
    printArea($shape);
}
```

**[⬆ กลับไปด้านบน](#สารบัญ)**

### Interface Segregation Principle (ISP)

ISP states that "Clients should not be forced to depend upon interfaces that
they do not use." 

A good example to look at that demonstrates this principle is for
classes that require large settings objects. Not requiring clients to set up
huge amounts of options is beneficial, because most of the time they won't need
all of the settings. Making them optional helps prevent having a "fat interface".

**Bad:**

```php
interface Employee
{
    public function work(): void;

    public function eat(): void;
}

class Human implements Employee
{
    public function work(): void
    {
        // ....working
    }

    public function eat(): void
    {
        // ...... eating in lunch break
    }
}

class Robot implements Employee
{
    public function work(): void
    {
        //.... working much more
    }

    public function eat(): void
    {
        //.... robot can't eat, but it must implement this method
    }
}
```

**Good:**

Not every worker is an employee, but every employee is a worker.

```php
interface Workable
{
    public function work(): void;
}

interface Feedable
{
    public function eat(): void;
}

interface Employee extends Feedable, Workable
{
}

class Human implements Employee
{
    public function work(): void
    {
        // ....working
    }

    public function eat(): void
    {
        //.... eating in lunch break
    }
}

// robot can only work
class Robot implements Workable
{
    public function work(): void
    {
        // ....working
    }
}
```

**[⬆ กลับไปด้านบน](#สารบัญ)**

### Dependency Inversion Principle (DIP)

This principle states two essential things:
1. High-level modules should not depend on low-level modules. Both should
depend on abstractions.
2. Abstractions should not depend upon details. Details should depend on
abstractions.

This can be hard to understand at first, but if you've worked with PHP frameworks (like Symfony), you've seen an implementation of this principle in the form of Dependency
Injection (DI). While they are not identical concepts, DIP keeps high-level
modules from knowing the details of its low-level modules and setting them up.
It can accomplish this through DI. A huge benefit of this is that it reduces
the coupling between modules. Coupling is a very bad development pattern because
it makes your code hard to refactor.

**Bad:**

```php
class Employee
{
    public function work(): void
    {
        // ....working
    }
}

class Robot extends Employee
{
    public function work(): void
    {
        //.... working much more
    }
}

class Manager
{
    private $employee;

    public function __construct(Employee $employee)
    {
        $this->employee = $employee;
    }

    public function manage(): void
    {
        $this->employee->work();
    }
}
```

**Good:**

```php
interface Employee
{
    public function work(): void;
}

class Human implements Employee
{
    public function work(): void
    {
        // ....working
    }
}

class Robot implements Employee
{
    public function work(): void
    {
        //.... working much more
    }
}

class Manager
{
    private $employee;

    public function __construct(Employee $employee)
    {
        $this->employee = $employee;
    }

    public function manage(): void
    {
        $this->employee->work();
    }
}
```

**[⬆ กลับไปด้านบน](#สารบัญ)**

## Don’t repeat yourself (DRY)

Try to observe the [DRY](https://en.wikipedia.org/wiki/Don%27t_repeat_yourself) principle.

Do your absolute best to avoid duplicate code. Duplicate code is bad because 
it means that there's more than one place to alter something if you need to 
change some logic.

Imagine if you run a restaurant and you keep track of your inventory: all your 
tomatoes, onions, garlic, spices, etc. If you have multiple lists that
you keep this on, then all have to be updated when you serve a dish with
tomatoes in them. If you only have one list, there's only one place to update!

Often you have duplicate code because you have two or more slightly
different things, that share a lot in common, but their differences force you
to have two or more separate functions that do much of the same things. Removing 
duplicate code means creating an abstraction that can handle this set of different 
things with just one function/module/class.

Getting the abstraction right is critical, that's why you should follow the
SOLID principles laid out in the [Classes](#classes) section. Bad abstractions can be
worse than duplicate code, so be careful! Having said this, if you can make
a good abstraction, do it! Don't repeat yourself, otherwise you'll find yourself 
updating multiple places any time you want to change one thing.

**Bad:**

```php
function showDeveloperList(array $developers): void
{
    foreach ($developers as $developer) {
        $expectedSalary = $developer->calculateExpectedSalary();
        $experience = $developer->getExperience();
        $githubLink = $developer->getGithubLink();
        $data = [
            $expectedSalary,
            $experience,
            $githubLink
        ];

        render($data);
    }
}

function showManagerList(array $managers): void
{
    foreach ($managers as $manager) {
        $expectedSalary = $manager->calculateExpectedSalary();
        $experience = $manager->getExperience();
        $githubLink = $manager->getGithubLink();
        $data = [
            $expectedSalary,
            $experience,
            $githubLink
        ];

        render($data);
    }
}
```

**ดี:**

```php
function showList(array $employees): void
{
    foreach ($employees as $employee) {
        $expectedSalary = $employee->calculateExpectedSalary();
        $experience = $employee->getExperience();
        $githubLink = $employee->getGithubLink();
        $data = [
            $expectedSalary,
            $experience,
            $githubLink
        ];

        render($data);
    }
}
```

**ดีมาก:**

ใช้โค้ดที่สั้นกระชับเป็นการดีที่สุด

```php
function showList(array $employees): void
{
    foreach ($employees as $employee) {
        render([
            $employee->calculateExpectedSalary(),
            $employee->getExperience(),
            $employee->getGithubLink()
        ]);
    }
}
```

**[⬆ กลับไปด้านบน](#สารบัญ)**

## การแปล

บทความนี้มีในภาษาอื่นด้วย:

* :cn: **Chinese:**
   * [php-cpm/clean-code-php](https://github.com/php-cpm/clean-code-php)
* :ru: **Russian:**
   * [peter-gribanov/clean-code-php](https://github.com/peter-gribanov/clean-code-php)
* :es: **Spanish:**
   * [fikoborquez/clean-code-php](https://github.com/fikoborquez/clean-code-php)
* :brazil: **Portuguese:**
   * [fabioars/clean-code-php](https://github.com/fabioars/clean-code-php)
   * [jeanjar/clean-code-php](https://github.com/jeanjar/clean-code-php/tree/pt-br)
* :thailand: **Thai:**
   * [panuwizzle/clean-code-php](https://github.com/panuwizzle/clean-code-php)
* :fr: **French:**
   * [errorname/clean-code-php](https://github.com/errorname/clean-code-php)
* :vietnam: **Vietnamese**
   * [viethuongdev/clean-code-php](https://github.com/viethuongdev/clean-code-php)
* :kr: **Korean:**
   * [yujineeee/clean-code-php](https://github.com/yujineeee/clean-code-php)
   
**[⬆ กลับไปด้านบน](#สารบัญ)**
