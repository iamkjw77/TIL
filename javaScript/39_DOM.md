## JAVASCRIPT
<details open>
<summary>DOM</summary>
<div markdown="39">

```html
<!DOCTYPE html>
<html lang="ko">
<head>
</head>
<body>
  <input type="text" id="user" class="bar" value="jiwon" />
</body>
<script>
  const $input = document.getElementById('user');

  $input.class = 'foo';
  console.log($input.class); // foo
  console.log($input.getAttribute('class')); // bar
</script>
</html>
```
```html
<!DOCTYPE html>
<html lang="ko">
<head>
</head>
<body>
  <div class="div" style="color: red">Hello World</div>
</body>
<script>
  const $div = document.querySelector('div');

  $div.className = 'abc';

  console.log($div.className); // abc
  console.log($div.getAttribute('class')); // abc

  console.log($div.class); // undefined
  console.log($div.getAttribute('className')); // null
</script>
</html>
```

</div> 
</details>

---