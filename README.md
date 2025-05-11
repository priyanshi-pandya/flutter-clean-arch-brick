# Flutter Clean Architecture Brick 🧱

A Mason brick template that helps you scaffold a clean architecture structure for your Flutter
applications quickly and consistently.

[![Powered by Mason](https://img.shields.io/badge/Powered%20by-Mason-blue)](https://github.com/felangel/mason)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

## Overview

This brick generates a feature folder structure following clean architecture principles, helping you
maintain a scalable and testable Flutter application. It separates your code into data, domain, and
presentation layers to ensure separation of concerns.

## Features

- 🏗️ Scaffolds a complete feature with all necessary layers
- 🧩 Implements dependency injection setup
- 🔄 Creates repository pattern implementation
- 📱 Generates presentation layer with state management
- ✅ Includes test directories for each layer

## Installation

```bash
# Install mason_cli if not already installed
dart pub global activate mason_cli

# Add this brick locally
mason add flutter_clean_arch --git-url https://github.com/priyanshi-pandya/flutter-clean-arch-brick.git --git-path .

# Or add from brick registry if published
# mason add flutter_clean_arch
```

## Usage

```bash
# Generate a new feature
mason make flutter_clean_arch -o lib/features --feature_name user_profile
```

### Variables

| Variable | Description | Default | Required |
| --- | --- | --- | --- |
| `feature_name` | Name of the feature to generate (snake_case) | - | Yes |

## Generated Structure

```
feature_name/
├── data/
│   ├── datasources/
│   │   ├── local/
│   │   └── remote/
│   ├── models/
│   └── repositories/
├── domain/
│   ├── entities/
│   ├── repositories/
│   └── usecases/
└── presentation/
    ├── bloc/
    ├── pages/
    └── widgets/
```

## Example

Here's an example of what a feature named "user_authentication" would look like after generation:

```
user_authentication/
├── data/
│   ├── datasources/
│   │   ├── local/
│   │   │   └── user_auth_local_data_source.dart
│   │   └── remote/
│   │       └── user_auth_remote_data_source.dart
│   ├── models/
│   │   └── user_model.dart
│   └── repositories/
│       └── user_auth_repository_impl.dart
├── domain/
│   ├── entities/
│   │   └── user.dart
│   ├── repositories/
│   │   └── user_auth_repository.dart
│   └── usecases/
│       ├── get_user.dart
│       ├── login_user.dart
│       └── logout_user.dart
└── presentation/
    ├── bloc/
    │   ├── user_auth_bloc.dart
    │   ├── user_auth_event.dart
    │   └── user_auth_state.dart
    ├── pages/
    │   ├── login_page.dart
    │   └── register_page.dart
    └── widgets/
        └── auth_form.dart
```

## Best Practices

- Keep each feature's code within its own directory
- Follow the dependency rule: outer layers can depend on inner layers, but not vice versa
- Implement proper error handling in each layer
- Write tests for each component in the respective test directories

## Customization

You can modify the brick to fit your specific project needs:

1. Clone this repository
2. Modify the brick templates in the `__brick__` directory
3. Update the `brick.yaml` file if needed
4. Use it locally or publish your modified version
