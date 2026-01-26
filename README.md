# Vue Lesson 18 - Component Communication

## What I Learned (Assignment)

This lesson covered **parent-child component communication** in Vue.js:
- Passing data from parent to child using **props**
- Sending data from child to parent using **custom events** (`$emit`)

## Challenges

Understanding how data flows between components when writing code is challenging, especially:
- Knowing when to use `props` vs `$emit`
- Parent must listen for events, otherwise child's `$emit` is ignored (caused a bug)
- Matching data format between emitter and receiver (object vs separate arguments)

## Memo: Vue Shorthands

| Shorthand | Full Syntax | Purpose | Direction |
|-----------|-------------|---------|-----------|
| `:` | `v-bind:` | Pass props to child | Parent → Child |
| `@` | `v-on:` | Listen for events | Child → Parent |

### Data Flow Pattern

```
Parent (App.vue)
    │
    ├── props (↓)     :username="user.name"
    │
    └── events (↑)    @set-data="setUserData"

Child (UserData.vue)
    └── this.$emit('set-data', { name, age })
```

### Example Usage

```vue
<!-- Parent: passing props and listening for events -->
<child-component
  :prop-name="value"
  @event-name="handlerMethod">
</child-component>

<!-- Child: receiving props and emitting events -->
<script>
export default {
  props: ['propName'],
  emits: ['event-name'],
  methods: {
    doSomething() {
      this.$emit('event-name', payload)
    }
  }
}
</script>
```

### Type Conversion

```javascript
// Input values are always strings
+data.age              // Unary plus (shortest)
Number(data.age)       // Number constructor
parseInt(data.age, 10) // Parse integer
```
