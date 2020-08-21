# react-photo-view




## 

    yarn add react-photo-view



```js
import { PhotoProvider, PhotoConsumer } from 'react-photo-view';
import 'react-photo-view/dist/index.css';

function ImageView() {
  return (
    <PhotoProvider>
      {photoImages.map((item, index) => (
        <PhotoConsumer key={index} src={item} intro={item}>
          <img src={item} alt="" />
        </PhotoConsumer>
      ))}
    </PhotoProvider>
  );
}
```

受控 `PhotoSlider`

```js
function ImageView() {
  const [visible, setVisible] = React.useState(false);
  const [photoIndex, setPhotoIndex] = React.useState(0);

  return (
    <div>
      <Button onClick={() => setVisible(true)}>打开</Button>
      <PhotoSlider
        images={photoImages.map(item => ({ src: item }))}
        visible={visible}
        onClose={() => setVisible(false)}
        index={photoIndex}
        onIndexChange={setPhotoIndex}
      />
    </div>
  );
}
```

### API

#### PhotoProvider

| Name           | Type                              | Select | Des                       |
| :------------- | :-------------------------------- | :--- | :------------------------- |
| children       | React.ReactNode                   | Y   |                            |
| maskClosable   | boolean                           | N   | bc，def true  |
| photoClosable  | boolean                           | N   | pc，def false |
| bannerVisible  | boolean                           | N   | navigate visible，def true  |
| introVisible   | boolean                           | N   | breif visible，def true    |
| overlayRender  | (overlayProps) => React.ReactNode | N   | custom                 |
| toolbarRender  | (overlayProps) => React.ReactNode | N   | tools               |
| className      | string                            | N   | className                  |
| maskClassName  | string                            | N   |  className             |
| viewClassName  | string                            | N   | picture Container className         |
| imageClassName | string                            | N   | picture className             |
| loadingElement | JSX.Element                       | N   | custom loading             |

