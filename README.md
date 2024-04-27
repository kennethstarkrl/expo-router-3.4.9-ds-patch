# Expo Router V3.4.9 Dynamic Screens Patch

This unofficial patch allows you to pass the slug param to the options rather than using the name as React Navigation conflicts with the name.

You'll want to set the slug param in the options object to the path of your slug file.

This patch is still backwards compatable so you could have screen compnents outside the map that use the slug file path as the name.

### **Example useage**
```js
export default function TabsLayout(){
   const [tabs,setTabs] = useState([])
   useEffect(()=>{
       //fetch whatever data for each tab
       setTabs(
        [{
          id:1,
          title:'tab1'
        },
        {
          id:2,
          title:'tab2'
        },
        {
          id:3,
          title:'tab3'
        }]
      );
   },[]);
   return(
      <Tabs>
      {tabs.map((tab,index)=>{
             return(
                  <Tabs.Screen
                         key={tab.id}
                         name={tab.title}
                         options={{
                            href:`tabs/${tab.id}`,
                            title:tab.title,
                            slug:'[tabs]'
                          }}
                   />
             )
       })}
      </Tabs>
   )
}
```
Check out the [Expo Router documentation](https://docs.expo.dev/routing/introduction/) for more information.
