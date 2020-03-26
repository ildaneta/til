# Today I Learned

Today I learned how to use [**Knex**](http://knexjs.org/) on the backend, due to the learnings of Rocketseat's Omnistack 11 Week. The way we create migrations and database selects is very intuitive, I felt very comfortable using it.

`npx knex migrate:make nameOfMigration`

```javascript
// Method UP creates tables
exports.up = function(knex) {
  // Creating the table
  return knex.schema.createTable('incidents', function(table) {
    // Creating the column
    table.string('id').primary();
    // To use a numeric type column id and auto-increment
    table.increments();
    table.string('name').notNullable();
    table.string('uf', 2).notNullable();
    table.decimal('value').notNullable();

    // Foreing Key
    table.string('ong_id').notNullable();

    // Referencing the foreing key of ONGs table
    table
      .foreign('ong_id')
      .references('id')
      .inTable('ongs');
  });
};

/* Method Down if for doing when something goes wrong, 
  in that case I would delete the table */
exports.down = function(knex) {
  return knex.schema.dropTable('incidents');
};
```

One very interesting thing that I learned was to separate all the routes of a certain entity in Controllers, it was an unusual way for me in the backend, but I really liked it, because it organizes our code a lot.
