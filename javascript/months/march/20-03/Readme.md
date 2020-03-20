# Today I Learned 20-03

Today I learned, well, properly saying, I had already done it once, but I used in the project that I'm acting menus that have submenus.

When you click on the menu, it changes styles, symbol and displays the items it has inside.

For this, we use Hooks:

```javascript
const [actived, setActived] = useState("");

return (
  {arrayOfMenus.map((item, index) => (
    <div key={arrayOfMenus.index} onClick={() => setActived(arrayOfMenus[index])}>
      <ul>
        <li className={actived === item.menuName[index] ? "menuActived" : ""}>
          {item.menuName}
        </li>
        <button>
          {actived === item.menuName[index] ? (<ArrowUp className="activedArrow" />)
          : (<ArrowDown />)}
        </button>
      </ul>

      {actived === item.menuName[index] && (<SubMenus />)}

    </div>
  )
)
```

It's very simple, we start our hooks as empty and when there is ac click() our actived will receive the item in the map position (in our index).

So after that, we just nedd to check if the item is active and if the item that is active is the same one that was clicked, that is, the same position and the same item.
