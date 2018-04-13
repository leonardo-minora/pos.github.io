

# [](#header-1) Container : UI : ReactNative


## [](#header-2) Introdução

**objetivos**:
- iniciar a estrutura do código-fonte do projeto para futuras adições de componentes e telas;
- Criar uma tela inicial do aplicativo;
- Criar um componente Container.

### [](#header-3) componentes react native

1. [StatusBar](https://facebook.github.io/react-native/docs/statusbar.html): é um componente que controla a barra de status do aplicativo.
2. [View](https://facebook.github.io/react-native/docs/view.html): é um container para outros componentes.

## [](#header-2) Códigos-fonte

[snack expo](https://snack.expo.io/@leonardo-minora/tiipos-2018-rn-02-app)


**app/components/Container/Container.js**
```jsx
import PropTypes from 'prop-types';
import React from 'react';
import { View } from 'react-native';

import styles from './styles';

const Container = ({ children }) => (
  <View style={styles.container}>
    {children}
  </View>
);

Container.propTypes = {
  children: PropTypes.any,
};

export default Container;
```


**app/components/Container/index.js**
```jsx
import Container from './Container';
import styles from './styles';

export { Container, styles };
```

**app/components/Container/styles.js**
```jsx
import EStyleSheet from 'react-native-extended-stylesheet';

export default EStyleSheet.create({
  container: {
    flex: 1,
    alignItems: 'center',
    justifyContent: 'center',
    backgroundColor: '$primaryBlue',
  },
});
```


**app/screens/Home.js**
```jsx
import React from 'react';
import { StatusBar } from 'react-native';

import { Container } from '../components/Container';

export default () => (
  <Container>
    <StatusBar translucent={false} barStyle="light-content" />
  </Container>
);
```

**app/index.js**
```jsx
import React from 'react';
import EStyleSheet from 'react-native-extended-stylesheet';

import Home from './screens/Home';

EStyleSheet.build({
  $primaryBlue: '#4F6D7A',
});

export default () => <Home />;
```

**App.js**
```jsx
import App from './app/index';
 
export default App;
```
