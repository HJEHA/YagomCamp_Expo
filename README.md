
## ๐ฐ๐ท ๋ง๊ตญ๋ฐ๋ํ

#### ๐๏ธ ํ๋ก์ ํธ ๊ธฐ๊ฐ: 2021.12.06 - 2021.12.17

#### Contributor
๐ถ [Allie](https://github.com/wooyani77) ๐ฆ [ํํฉ](https://github.com/hwangjeha) ๐น [์ ๋ฆฌ](https://github.com/llghdud921)

#### Reviewer
๐ [๋๋ฏธ๋](https://github.com/AppleCEO)


## โ UML

![](https://i.imgur.com/sY2NLVO.jpg)


## โ๏ธํ์ต ํค์๋
- JSON data Parsing
- TableView
- AutoLayout
- Accessibilty
- Custom View
- ํ๋ฉด ํ์ 


## ํ๋ก์ ํธ ์ค๋ช

### โ๏ธ ๊ตฌํ๋ชจ์ต
![](https://i.imgur.com/5OUVpro.gif)


#### [**JSON Data๋ฅผ ์ด์ฉํ ํ์ด๋ธ ๋ทฐ ์ฑ**]
โ๏ธ ํ๋ฆฌ ๋ง๊ตญ๋ฐ๋ํ์ ๋ํ ์ ๋ณด์ ์ถํ์ ๋ณด๋ฌ๊ฐ๊ธฐ ๊ธฐ๋ฅ 

โ๏ธ ํ๋ฆฌ ๋ฐ๋ํ์ ํ๊ตญ ์ถํ์ ๋ฆฌ์คํธ TableView๋ก ๊ตฌํ

โ๏ธ ๋ฆฌ์คํธ ์ถํ์ ํด๋ฆญ ์ ์์ธ ์ค๋ช ํ๋ฉด ๋ณด์ฌ์ฃผ๋ ๊ธฐ๋ฅ

โ๏ธ ์ฑ ๋ด ๋ชจ๋  ํ์คํธ์ ์ด๋ฏธ์ง์ VoiceOver ๋ฐ Dynamic Font ์ ์ฉ

<br> 

## Step 1. ๋ชจ๋ธ ํ์ ๊ตฌํ

### ๐ก 1-1. ๊ตฌํ ๋ด์ฉ

- JSON ํฌ๋ฉง๊ณผ ๋งค์นญํ  ๋ชจ๋ธ ํ์ ๊ตฌํ
- CodingKeys๋ฅผ ํ์ฉํด JSON Data Key์ ํ๋กํผํฐ ๋ช ๋งค์นญ 
- JSONDecoder() ์ฌ์ฌ์ฉ์ฑ์ ์ํด ์ ๋ค๋ฆญ ํ์ ๋ฉ์๋ `decode()` ๊ตฌํ
- `decode()` Unit Test 




<br>


## Step 2. ํ๋ฉด ๊ตฌํ

### ๐ก 2-1. ๊ตฌํ ๋ด์ฉ

- TableView๋ฅผ ํ์ฉํ ๋ฆฌ์คํธ ํ๋ฉด ๊ตฌํ
- CustomView๋ก ๊ตฌํํ๊ณ  awakeFromNib๋ฅผ ์ด์ฉํ์ฌ ๊ฐ View์ ์ด๊ธฐ์ค์  ๊ตฌํ  
- Navigation Controller๋ฅผ ํ์ฉํ ํ๋ฉด ์ ํ
- NavigationBar ํ์ฑํ/๋นํ์ฑํ ๊ตฌํ

### โ 2-2. ๊ณ ๋ฏผํ๋ ์ 
- `awakeFromNib()`
    
    StoryBoard์์ View๋ฅผ ๊ตฌ์ฑํ๊ณ  CustomView ํด๋์ค์ IBOutlet์ผ๋ก View์ ์ฐ๊ฒฐํ๋ ๋ฐฉ์์ ์ฌ์ฉํ์ต๋๋ค.
    
    `awakeFromNib()`์ ์ฌ์ฉํ๊ธฐ์  CustomView ๋ด๋ถ `init()`์์ `setUp()` ๋ฉ์๋๋ฅผ ์ฌ์ฉํ์ฌ ์ด๊ธฐ์ค์ ์ ํ๋ ค ํ์ผ๋ 
    
    ์ค๋ฅ๊ฐ ๋ฐ์ํด ์์ธ์ ์ฐพ์๋ณด๋ ๋ทฐ ์ปจํธ๋กค๋ฌ `loadView()`๋ฉ์๋๊ฐ ํธ์ถ๋๊ธฐ ์  CustomView ๋ด๋ถ `init()`์ด ๋จผ์  ํธ์ถ๋์ด
    
    ๋ฉ๋ชจ๋ฆฌ ์ฌ๋ผ๊ฐ์ง ์์ ๋ทฐ์ ์ ๊ทผํ๋ ค ํด์ ์๊ธด ๋ฌธ์ ์์ต๋๋ค.
    
    `awakeFromNib()` ๋ฉ์๋๋ View๊ฐ ์ธ์คํด์คํ ๋ ์งํ ํธ์ถ๋๊ธฐ ๋๋ฌธ์
    
    ์ปค์คํ ๋ทฐ ์ด๊ธฐ์ค์ ์ `awakeFromNib()`๋ด๋ถ์์ ํธ์ถํด ์คฌ์ต๋๋ค.
    
    ```swift
    override func awakeFromNib() {
        super.awakeFromNib()
        setUp() // ์ปค์คํ ๋ทฐ ์ด๊ธฐ ์ค์ ํ๋ ๋ฉ์๋
    }
    ```
    
- Navigation Controller ํ์ฑํ/๋นํ์ฑํ ํธ์ถ ์์น
    
    ์ฒซ๋ฒ์งธ main ํ๋ฉด์์๋ navigation Bar Item์ ๋ํ๋ด์ง ์๊ธฐ ์ํด์ ViewLifeCycle ๋ฉ์๋๋ฅผ ์ด์ฉํด `isNavigationBarButton` ์์ฑ์ ์ด์ฉํ์์ต๋๋ค.
    
    - ViewWillAppear : ํ๋ฉด์ด ๋ํ๋๊ธฐ ์ ์ navigationBarButton์ ์จ๊น
    - viewWillDisappear : ํ๋ฉด์ด ์ฌ๋ผ์ง๊ณ  ๋์ navigationBarButton๋ฅผ ๋ํ๋
    
    ```swift
    override func viewWillAppear(_ animated: Bool) {
        super.viewWillAppear(animated)
        self.navigationController?.isNavigationBarHidden = true
    }
        
    override func viewWillDisappear(_ animated: Bool) {
        viewWillDisappear(animated)
        self.navigationController?.isNavigationBarHidden = false
    }
    ```


- Custom Cell ๊ตฌ์ฑ ๋ฐฉ๋ฒ
    1. `Xib ํ์ผ๋ก Cell View ๊ตฌ์ฑ`
    2. `StoryBoard์ Cell View ๊ตฌ์ฑ`
    
    Cell View๋ฅผ ๊ตฌ์ฑํ  ๋ ๋ ๊ฐ์ง ๋ฐฉ์ ๋ชจ๋ ์ ์ฉํด๋ดค์ต๋๋ค.
    
    2๋ฒ ๋ฐฉ์ `StoryBoard์ Cell View ๊ตฌ์ฑ` ๋ฐฉ๋ฒ์ ์ ํํ ์ด์ ๋ `๋ง๊ตญ๋ฐ๋ํ ์ฑ`์๋ ํ๋์ TableView๋ฅผ ๊ฐ์ง๊ณ  ์์ด `Xib ํ์ผ์ ์ฅ์ ์ธ View ์ฌ์ฌ์ฉ์ฑ`์ ์ด์ ์ ๊ฐ์ง์ง ๋ชปํ๋ค๊ณ  ํ๋จํ์ต๋๋ค.
    

<br>

## Step 3. ์คํ ๋ ์ด์์ ์ ์ฉ

### ๐ก 3-1. ๊ตฌํ ๋ด์ฉ
- ์ฒซ ํ๋ฉด์ ์ธ๋ก๋ฐฉํฅ ๊ณ ์ 
- ๋ชจ๋  ํ๋ฉด์ด ๋ค๋ฅธ ์์ดํฐ ๊ธฐ๊ธฐ์์๋ ์๋ง์ ํฌ๊ธฐ๋ก ๋ณด์ฌ์ง๋๋ก ๊ตฌํ
- Dynamic Type ์ ์ฉ
- ํ์คํธ๊ฐ ์๋ฆฌ๊ฑฐ๋ ์ค์ํ(โฆ) ์ฒ๋ฆฌ๊ฐ ๋์ง ์๋๋ก ๊ตฌํ

### โ 3-2. ๊ณ ๋ฏผํ๋ ์ 
- ํ๋ฉด ๋ฐฉํฅ ๊ณ ์ ์ ๋ํ ๊ณ ๋ฏผ
    
    ๊ฐ `ViewController`์ `supportedInterfaceOrientations` ๋ฅผ ์ง์ ํ๊ธฐ ๋ณด๋ค ์์์ ์๋ `Controller`์ธ  `navigationController` ์์ ํ๋ฉด ๋ฐฉํฅ์ ์ปจํธ๋กค ํ๋ ๊ฒ์ด override ์ธก๋ฉด์์ ์์ ํ๊ณ  
    
    ๊ฐ `ViewController`์์ ๋ฐฉํฅ์ ๊ด๋ฆฌํ๋ ๊ฒ๋ณด๋ค ์ฉ์ดํ๋ค๊ณ  ์๊ฐํ์ต๋๋ค.
    
    `navigationController`๋ด๋ถ์ `topViewController` ์ฆ, ํ์ฌ ํ๋ฉด์ ๊ฐ์ฅ ์์์ ์์นํ `ViewController` ์ ๋ณด๋ฅผ ๋ฐ์์ ํ๋ฉด ๋ฐฉํฅ์ ์กฐ์ ํด์ฃผ์์ต๋๋ค.
    
    ```swift
    override var supportedInterfaceOrientations: UIInterfaceOrientationMask {
        if let _ = self.topViewController as? ExpoInformationViewController {
            return .portrait
        } else {
            return .all
        }
    }
    ```
    

- Label ๋ด๋ถ ํ์คํธ์ ์ฌ์ด์ฆ๋ฅผ ๊ฐ๊ฐ ๋ค๋ฅด๊ฒ ์ง์ ํด์ฃผ๊ธฐ์ํด `NSMutableAttributedString` ์ ์ฉ
    
    <img src="https://i.imgur.com/8pyXdyE.png" width="300" height="100">
    
    ```swift
    // extension์ผ๋ก ๋ฉ์๋ ๊ตฌํ
    extension NSMutableAttributedString {
        func setTextSize(string: String, fontSize: UIFont.TextStyle) -> Self {
            let attributes: [NSAttributedString.Key: Any] = [.font: UIFont.preferredFont(forTextStyle: fontSize)]
            self.append(NSAttributedString(string: string, attributes: attributes))
            return self
        }
    }
    visitorsLabel.attributedText = NSMutableAttributedString().setTextSize(string: "๋ฐฉ๋ฌธ๊ฐ", fontSize: .title3).setTextSize(string: " : \(visitors) ๋ช" , fontSize: .body)
    ```

    

- ๋ฒํผ title ๊ฐํ ๊ด๋ จ ๋ฌธ์ 
    
    button์ dynamic font๋ฅผ ์ ์ฉํ๊ณ  ์ผ์  ํฌ๊ธฐ ์ด์์ ์ปค์ง๋ฉด ๋ฒํผ์ ํ์ดํ์ ๊ฐํ์ด ์ผ์ด๋ฌ์ต๋๋ค.  
    `numberOfLines = 1` ๋ก ์ค์ ํ๊ฒ ๋๋ฉด ๊ฐํ์ด ๋์ง ์์ ์ค ์์๋๋ฐ ๊ฐํ์ด ๋๋ ํ์์ด ๋ฐ์ํ์ต๋๋ค.
    
    <img src="https://i.imgur.com/74Opj4P.png)" width="200" height="150">

    
    ```swift
    // 1. numberOfLines ์ค์  ์๋จ.
    // ํ์ง๋ง ๋ฒํผ์ ๋๋ ์ ๋ title์ด button์ผ๋ก ๋ฐ๋.
    entryListButton.titleLabel?.text = "ํ๊ตญ์ ์ถํ์ ๋ณด๋ฌ๊ฐ๊ธฐ"
    entryListButton.titleLabel?.numberOfLines = 1 
    ```
    
    <img src="https://i.imgur.com/n2Yol6q.png" width="200" height="150">

    
    ```swift
    // 2. numberOfLines ์ค์  ์๋จ.
    entryListButton.setTitle("ํ๊ตญ์ ์ถํ์ ๋ณด๋ฌ๊ฐ๊ธฐ", for: .normal)
    entryListButton.titleLabel?.numberOfLines = 1 
    ```
    
    ๊ณ ๋ฏผํด๋ณธ ๊ฒฐ๊ณผ ๋ฒํผ ์คํ์ผ ๋ฌธ์ ์๋ค๋ ๊ฒ์ ์๊ฒ๋์์ต๋๋ค
    
    ์คํ ๋ฆฌ๋ณด๋์์ ๋ฒํผ์ ์์ฑํ๊ฒ ๋๋ฉด ๋ฒํผ ์คํ์ผ์ด ๊ธฐ๋ณธ์ ์ผ๋ก `Plain`์ผ๋ก ์์ฑ๋๋๋ฐ `Default`๋ก ์ค์ ์ ๋ฐ๊ฟ์ ํ์คํธ ํด๋ณด๋ ์ ์์ ์ผ๋ก `numberOfLines = 1` ๋์ํ๋ ๊ฒ์ ํ์ธํ์ต๋๋ค.
    
    ์ด๋ฅผ ํตํด ๋ฒํผ ์คํ์ผ `Plain`, `Default` ๋ฑ ์คํ์ผ ๋ณ ์ฐจ์ด๋ฅผ ์๊ฒ๋์์ต๋๋ค.

<br>

### ๐ข 3-3. Trouble Shooting

- ๋ํ์ผ ๋ทฐ์์ ์ด๋ฆ์ด ๊ธด entry๋ค์ `back button`์ด "ํ๊ตญ์ ์ถํ์"์ด ์๋ "Back"์ผ๋ก ๋์ค๋ ๊ฒ์ ํ์ธํ์ต๋๋ค. 

    ํด๋น ๋ฌธ์ ๊ฐ dynamic Font์ ์ ์ฉํ  ๋ ๊ธ์๊ฐ ์ปค์ง๋ฉด ์งค๋ฆฌ๋ ๋ฌธ์ ๋ฅผ ๋ฐ๊ฒฌํ์ฌ `navigationBar`์ `title`์ ์ฌ์ด์ฆ๋ฅผ ์๊ฒ ๊ณ ์ ์์ผฐ๋๋ฐ๋ ํด๊ฒฐ๋์ง ์์์ต๋๋ค.

    ![](https://i.imgur.com/Ga3fCUL.png)
    
    **๋ฌธ์  ํด๊ฒฐ ์๋**

    ์๋ ์ฝ๋๋ฅผ ์ด์ฉํด์ title ํ์คํธ๋ฅผ ๋์ ์ผ๋ก ๋ณํํ๋ ๊ฒ์ ๋ฐฉ์งํด๋ณด์์ง๋ง
    ๋์ผํ ๊ฒฐ๊ณผ๊ฐ ๋ฐ์ํ์ต๋๋ค.
    
    ```swift
    let label = UILabel()
    label.text = entryData.name
    label.adjustsFontForContentSizeCategory = false
        
    self.navigationItem.titleView = label
    ```
    ![](https://i.imgur.com/5kQ3P0q.png)

    
