- 👋 Hi, I’m @melonkgur


- ``commands.spawn_bundle(NodeBundle {
        style: Style {
            size:  Size::new(Val::Percent(100.0), Val::Percent(100.0)),
            justify_content: JustifyContent::Center,
            position_type: PositionType::Absolute,
            align_items: AlignItems::Center,
            flex_direction: FlexDirection::Column,
            align_content: AlignContent::Center,
            ..default()
        },
        color: Color::rgb(0.20, 0.24, 0.31).into(),
        ..default()
    })
    .with_children(|parent| {

        parent.spawn_bundle( ImageBundle {
            style: Style {
                size: Size::new(Val::Px(240.0), Val::Px(130.0)),
                ..default()
            },
            image: source.load("images/yes.png").into(),
            ..default()
        })
        .with_children(|img| {
            img.spawn_bundle(ButtonBundle {
                style: Style {
                    size: Size::new(Val::Px(240.0), Val::Px(130.0)),
                    ..default()
                },
                color: Color::NONE.into(),
                ..default()
            }).insert(EnterButton);
        })
        .insert(Remove);

        parent.spawn_bundle( ImageBundle {
            style: Style {
                size: Size::new(Val::Px(100.0), Val::Px(100.0)),
                ..default()
            },
            image: source.load("images/svgarrow.png").into(),
            transform: Transform::from_rotation(Quat::from_rotation_z(PI)),
            ..default()
        })
        .with_children(|img| {
            img.spawn_bundle(ButtonBundle {
                style: Style {
                    size: Size::new(Val::Px(100.0), Val::Px(100.0)),
                    ..default()
                },
                color: Color::NONE.into(),
                ..default()
            }).insert(DownButton);
        })
        .insert(Remove);

        parent.spawn_bundle(
            TextBundle::from_section(
                "00:00", 
            TextStyle { 
                font: source.load("fonts/SourceSansPro-Regular.ttf"), 
                font_size: 100.0, 
                color: Color::WHITE 
            })
        ).insert(TimeOut);

        /*parent.spawn_bundle(ButtonBundle {
            style: Style {
                size: Size::new(Val::Px(100.0), Val::Px(100.0)),
                ..default()
            },
            color: Color::BEIGE.into(),
            ..default()
        }).with_children(|buttonparent| {
            buttonparent.spawn_bundle( ImageBundle {
                style: Style {
                    size: Size::new(Val::Px(100.0), Val::Px(100.0)),
                    ..default()
                },
                image: source.load("images/arrow.png").into(),
                ..default()
            });
        }).insert(UpButton);*/

        parent.spawn_bundle( ImageBundle {
            style: Style {
                size: Size::new(Val::Px(100.0), Val::Px(100.0)),
                ..default()
            },
            image: source.load("images/svgarrow.png").into(),
            ..default()
        }).with_children(|img| {
            img.spawn_bundle(ButtonBundle {
                style: Style {
                    size: Size::new(Val::Px(100.0), Val::Px(100.0)),
                    ..default()
                },
                color: Color::NONE.into(),
                ..default()
            }).insert(UpButton);
        }).insert(Remove);
    });
``
