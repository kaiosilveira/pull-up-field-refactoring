[![Continuous Integration](https://github.com/kaiosilveira/pull-up-field-refactoring/actions/workflows/ci.yml/badge.svg)](https://github.com/kaiosilveira/pull-up-field-refactoring/actions/workflows/ci.yml)

---

# Pull Up Field

<table>
<thead>
<th>Before</th>
<th>After</th>
</thead>
<tbody>
<tr>
<td>

```typescript
class Employee { ... }

class Salesman extends Employee {
  private name: string;
}

class Engineer extends Employee {
  private name: string;
}
```

</td>

<td>

```javascript
class Employee {
  protected name: string;
}

class Salesman extends Employee { ... }

class Engineer extends Employee { ... }
```

</td>
</tr>
</tbody>
</table>

**Inverse of: [Push Down Field](https://github.com/kaiosilveira/refactoring)**

When working with inheritance, sometimes we end up creating fields that seem particular to that subclass, but in fact was already added to another subclass in the hiearchy. This refactoring helps with these cases.

## Working example

Since Javascript is a dynamic language, and because in dynamic languages fields are defined the first time they're assigned to, the process of pulling up a field is the same of [pulling up a constructor's body](https://github.com/kaiosilveira/pull-up-constructor-body-refactoring).
