Bootstrap Grid Sort Column Widget for Yii2
====================================


Installation
------------
The preferred way to install this extension is through [composer](http://getcomposer.org/download/).

Either run

```
composer require greshnik/yii2-grid-sort-column "*"
```
or add

```json
"greshnik/yii2-grid-sort-column" : "*"
```

to the require section of your application's `composer.json` file.

Usage
-----

***Example***

```
<?= GridView::widget([
    'dataProvider' => $dataProvider,
    'filterModel' => $searchModel,
    'columns' => [
        ['class' => 'yii\grid\SerialColumn'],

        'id',
        'name',
        'class',

        ['class' => 'yii\grid\ActionColumn'],
        ['class' => 'app\gridSortColumn\SortColumn']
    ],
]); ?>
```  
***Example add sort action in controller***

```  
public function actions()
{
    return [
        'swap' => [
            'class' => 'app\gridSortColumn\Swap',
            'model' => new Mark,
            'attribute' => 'sortAttribute'
        ]
    ];
}
```

***Example add behavior in model***

```
public function behaviors()
{
    return [
        'sort' => [
            'class' => 'app\gridSortColumn\SortBehavior',
            'attribute' => 'sort'
        ]
    ];
}
```

License
-------

The BSD License (BSD). Please see [License File](LICENSE.md) for more information.