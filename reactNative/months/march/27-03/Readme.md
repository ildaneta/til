# Today I Learned

Today I learned a little more about React Native and I'm simply in love.

It's amazing how you have the base of Javascript + the knowledge of styling and rules of the frontend, give you a huge base to start developin in React Native.

Today I want to talk in particular about React Navigation version 5, which helps us to navigate between pages and for that I used Stack.

```javascript
import React from 'react';
import { NavigationContainer } from '@react-navigation/native';
import { createStackNavigator } from '@react-navigation/stack';

const AppStack = createStackNavigator();

import Incidents from './pages/Incidents';
import Detail from './pages/Detail';

function Routes() {
  return (
    <NavigationContainer>
      // ScreenOptions with the headerShown property's to disable the title that
      it puts by default
      <AppStack.Navigator screenOptions={{ headerShown: false }}>
        <AppStack.Screen name="Incidents" component={Incidents} />
        <AppStack.Screen name="Detail" component={Detail} />
      </AppStack.Navigator>
    </NavigationContainer>
  );
}

export default Routes;
```
