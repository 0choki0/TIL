# Basic command

**Markdown**의 basic 문법을 학습해보자.

[이곳](https://www.markdownguide.org/cheat-sheet/)에서 학습할 내용을 확인할 수 있다.

---
<br>

 - **Heading**

    Headinng은 첫 머리말에 사용한다. 구문은 `#`이며 #의 갯수에 따라 하위 헤더를 생성할 수 있다. #은 최대 6개까지 사용이 가능하다.

    # h1
    >`# h1`
    ## h2
    > `## h2`
    ### h3
    > `### h3`

<br>

- **Bold**

    Bold는 볼드체를 적용한다. 구문은 `** <텍스트> **` 이다. 

    **bold**
    > `**bold**`

<br>

- **Italic**
    
    Italic은 이텔릭체를 적용한다. 구문은 `* <텍스트> *` 이다.

    *Italicized text*
    > `*italicized text*`

<br>

- **Blockquote**

    Blockquote는 인용구를 적용합니다. 구문은 `>` 입니다.

    >blockquote
    
    >`>blockquote`

<br>

- **Order/Unorder List**

    리스트 작성에 사용합니다. 구문은 `n. / -` 입니다.

    1. frist item
    2. second item
    3. third item
    > `1. frist item`  
    `2. second item`  
    `3. third item`
    <br>
    - frist item
    - second item
    - third item
    > `- frist item`  
    `- second item`  
    `- third item`

<br>

- **Code**

    Code는 코드를 보여주는 역할을 합니다. 구문은 ``입니다. 각 backtick 사이에 메세지를 입력합니다.

    `code`
    >'code'

<br>

- **Horizontal  Rule**

    Horizontal Rule은 구역을 나누는 역할을 합니다. 구문은 `--- `입니다.

    a
    ---
    b
    > a  
    `---`  
    b

<br>

- **Link**

    Link는 텍스트에 URL주소를 입력할 수 있게 해줍니다. 구문은 `[title](URL)` 입니다.
    
    [Google](https://google.com)
    > `[Google](https://google.com)`

<br>

- **Image**

    Image는 이미지를 입력할 수 있게 해줍니다. 구문은 `![alt text](image.jpg)` 입니다. 대괄호에 이미지 이름을 적고, 소괄호에 이미지의 주소를 입력하면 됩니다. 다음의 예시는 구글의 인터넷 주소에서 가져온 이미지와 local에서 가져온 이미지 입니다.

    <br>

    ![Google_image](data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAHcAAAB6CAMAAACyeTxmAAABJlBMVEX////pQjU0qFNChfT6uwWAqvk5gfQzf/Tm7v690Pv6tgD6uQAwp1DpQDPpPC7/vADoOCklpEnn8+r63Nv98fD1sKz7wADoNjff8OPy+fT86ejrUkfoLBnoMSD4+v8QoT/sYlnudGzxj4nrST3nHQD4zszoJhD3phX/+vD7viX/9OD+8NL81IX95rj93Zb+35/94qpglvbd5/1DrV7R6NbC4cn3v7vynZjsWlD0pqHue3Txh4DtZmX1jwD80HHrVTDubSvyiCPweif1lh37xUjsTQn7xTrQ3vz8zFwhd/RJozXQtiaExZOauvmmsjh5rUWaz6beuB9Uqk3BtTCPsD+txvpmvYax2rpjuXMml5A1o3BAiec/kM4/mrA3n4kxpWI7k7yEsOVV1wY9AAAFRElEQVRoge2YaXvaRhDHhSyDDZLQIkwNSBaHIT5ip7E4fLTunYRGaUlaY9I2Pb7/l+iKW2J2pV1J+Hla/i/8xqCf5j8zO7MIwlZbbbXVZlSs6FNVipsi6r1+vVZtKupEqep1/e5AryQL1W/qVcPQVFVZkaqZbaXW6CUVud64NkxVSUHCcEO5TQBdvKkeazBzyTbMhh4rtXJnmHToDK0d11pxUgNCXZFqXMdDLjY0LSx0SjbrMbjda4Zy2CNNvYlIrdyyU7EUsxapo1sKm8VLqWaPH9s/5gl2FrLR4MXWDG6qK7PGdYxUqrwez6VVOepab6oRsdjqA2ZsKxUda7JjdeVJsJXo0aY4TBZiwLY5sLWolZxKHXNgG2bAQ90p324bhvvHhEYVTyULPfpxoWjt6m2/hze6It7uWgeNmmn4thAubKVJORwVzaz1dd85VOnV1dXxwVPJglCnJFdTb+GhXukvxyUftkdOLnWg4/Vg1gQ8JgvFFNFlrUlfYPTa5JV5GkgQ7kguK+27wC/32wpXA+E8kVwON8dbKl+0wheEg0pthhtpOh/2/EsCtprsBei+9Oyrz6Bok8WeZaVS7us1sKIlfN27zEmSVPrGD27Hd/WAJblcqfTMCzb7CWMvstJEJWk1yep1wljhPifNVPp2AVa0eK+W6zo5XXCl0ncbc1k4z0pLzRtKaSb+w8nznLQKnjaUGfVmF6zvPdxpQympxMM9k/zCDaUFD6Go8qR37vUPSRezILzIrXEl6RXtG6932fQafMobgJt7TuPuD9IsyuyCT/GXlavsBZWb2WHSS+ghJ68g7kmc3J0j4CHr5YxtPqVh2bl7wEPOofS+iZWbvgrLpZYVOxcq6Iv19pWyl7FyM/thuS82wIXK+fP/MPepfH6iutpAH4XnxntugFzwnJRi5YLnxgbmAnhOCiA31jkIc8G5fx8nF5yD4J6TO6UZvT/IEAVhwbkP7XV56ccOhXu0RxZkM8xdL+j8Wxk5FC7tlQbr3Mw7+LO+BSuX/0kURbnAxYVSD7av4L+n5KWfMVZEQy7ubhrgguXsS3D+/QcXK8o2T8BHYFmB5ey9h+Z/EWfiyvADYHMaXp+FlXt3Lv+ruBA6ZMYevQTCzTyQPj4fhXnpwxKLnWbm7gPVTEwv1tTo/HvRI2anwewS04t1mZ23j0dWl437Djqt0oTudXWSnbePL2KmFO8DPUS1GVfWvH28YmqmK9BlwuE809lbgMoGPtqBwyVW80QjmQCWaQNiRXswdidDripXhxbMFWX0GAZ7RcDSqmoiBxHAojUKxj5AjetqQA9XEMo2wWlc1WJAPx2OP6YJ4RLPyIW6xICx12NKlgsOktFvv4ObRjooXKwRGeySu2XwWx1HRBNP/oAmb1B2J+9NdtolW7bT8aHLneEYofn/PwHgEOFip0k1PY/ZEkfDx27BVaf76IxlC628qvWnv6Yz8A9XaxrSwRM2smZCyG8P+subZMLvVoDGlBSHkGz9vdpPlEHkFzXFIWR9zCy8hm8JsChdHE7LhhoQtkhYh5HBs4Ya0OdB/GAZfcKHV/iaig3sNhQ71j0/olW121D/sGOxRoF9HBAw5+UKHyARvJYR4zq4og6/18hm3/eXKjtrx2C4YC0Hnluh1eUJGdn8Hi9CHsqMZISGEYOdkR2LgYwsJ0pmPSoMUbjSxsPZ4fuFgKTu2AoqMQy143HYo4K7zZDYMoaOhyGXe3b0o2Mjd8WQ5QVPdpcPNB4NY8sqqHKhg1cq254iRdsej5zHTiF+e2F6uXDoqrAp4FZbbfW/179wN6bIyeplrwAAAABJRU5ErkJggg==)

    > `![Google_image](구글의 이미지 주소)`

    <br>

    ![Choki](./assets/choki.png)
    > `![Choki](./assets/choki.png)`

<br>

- **Fenced Code Block**

    Fenced Code Block은 프로그래밍 언어를 표시해줍니다. 하이라이트가 적용되어 보기 쉽게 표현되는 장점이 있습니다.

<br>

```python
def func():
    return True
```
> ` ```python`  
`def func():`  
`return True`  
` ``` `

---
<br>

```javascript
console.log('hello')
```
> ` ```javascript`  
`console.log('hello')`  
` ``` `

<br/>

---

오늘 배운 Markdown의 basic command는 위의 것들이다. 이를 이용해서 
