# My Clinic Android App

This project is an Android e-commerce/clinic application with a fully configured CI/CD pipeline.

## CI/CD Pipeline Documentation

The project uses **GitHub Actions** for Continuous Integration. The workflow is defined in `.github/workflows/android-ci.yml`.

### Workflow Stages

1.  **Code Quality Checks**:
    *   **Tooling**: Android Lint and Detekt.
    *   **Description**: Performs static code analysis to ensure code quality and adherence to style guides.
    *   **Artifacts**: HTML reports for both Lint and Detekt are uploaded.

2.  **Unit Tests**:
    *   **Tooling**: JUnit and JaCoCo.
    *   **Description**: Runs all local unit tests and generates a code coverage report.
    *   **Artifacts**: Test results and JaCoCo coverage reports.

3.  **Instrumented Tests**:
    *   **Tooling**: Android Emulator Runner (ReactiveCircus).
    *   **Description**: Runs UI tests on a matrix of Android API levels (28, 30, 33) using an emulator.
    *   **Artifacts**: Test reports for each API level.

4.  **Build Debug APK**:
    *   **Tooling**: Gradle `assembleDebug`.
    *   **Description**: Compiles the application and generates a debug APK.
    *   **Artifacts**: `app-debug.apk`.

### How to Run Locally

*   **Lint**: `./gradlew lintDebug`
*   **Detekt**: `./gradlew detekt`
*   **Unit Tests**: `./gradlew testDebugUnitTest`
*   **Coverage**: `./gradlew jacocoTestReport`
*   **Instrumented Tests**: `./gradlew connectedDebugAndroidTest`
*   **Build APK**: `./gradlew assembleDebug`
