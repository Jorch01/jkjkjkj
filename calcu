<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Calculadora de Finiquito y Liquidación - LFT 2025</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
            padding: 20px;
        }

        .container {
            max-width: 900px;
            margin: 0 auto;
            background: white;
            border-radius: 20px;
            box-shadow: 0 20px 60px rgba(0, 0, 0, 0.3);
            overflow: hidden;
        }

        .header {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 30px;
            text-align: center;
        }

        .header h1 {
            font-size: 2em;
            margin-bottom: 10px;
        }

        .header p {
            font-size: 1.1em;
            opacity: 0.9;
        }

        .progress-bar {
            background: rgba(255, 255, 255, 0.2);
            height: 10px;
            border-radius: 5px;
            margin-top: 20px;
            overflow: hidden;
        }

        .progress-fill {
            background: white;
            height: 100%;
            border-radius: 5px;
            width: 0%;
            transition: width 0.3s ease;
        }

        .form-container {
            padding: 40px;
        }

        .step {
            display: none;
            animation: fadeIn 0.3s ease;
        }

        .step.active {
            display: block;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(10px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .step-title {
            color: #667eea;
            font-size: 1.5em;
            margin-bottom: 10px;
            font-weight: 600;
        }

        .step-description {
            color: #666;
            margin-bottom: 25px;
            line-height: 1.5;
        }

        .form-group {
            margin-bottom: 25px;
        }

        label {
            display: block;
            margin-bottom: 8px;
            color: #333;
            font-weight: 500;
        }

        input[type="text"],
        input[type="number"],
        input[type="date"],
        select {
            width: 100%;
            padding: 12px;
            border: 2px solid #e0e0e0;
            border-radius: 8px;
            font-size: 1em;
            transition: border-color 0.3s;
        }

        input:focus,
        select:focus {
            outline: none;
            border-color: #667eea;
        }

        .radio-group,
        .checkbox-group {
            display: flex;
            flex-direction: column;
            gap: 12px;
        }

        .radio-option,
        .checkbox-option {
            display: flex;
            align-items: center;
            padding: 12px;
            border: 2px solid #e0e0e0;
            border-radius: 8px;
            cursor: pointer;
            transition: all 0.3s;
        }

        .radio-option:hover,
        .checkbox-option:hover {
            border-color: #667eea;
            background: #f8f9ff;
        }

        .radio-option input,
        .checkbox-option input {
            margin-right: 12px;
        }

        .radio-option.selected,
        .checkbox-option.selected {
            border-color: #667eea;
            background: #f8f9ff;
        }

        .button-group {
            display: flex;
            gap: 15px;
            margin-top: 30px;
        }

        button {
            padding: 12px 30px;
            border: none;
            border-radius: 8px;
            font-size: 1em;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s;
        }

        .btn-primary {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
        }

        .btn-primary:hover {
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(102, 126, 234, 0.4);
        }

        .btn-secondary {
            background: #e0e0e0;
            color: #333;
        }

        .btn-secondary:hover {
            background: #d0d0d0;
        }

        .alert {
            padding: 15px;
            border-radius: 8px;
            margin-bottom: 20px;
        }

        .alert-info {
            background: #e3f2fd;
            color: #1976d2;
            border-left: 4px solid #1976d2;
        }

        .alert-warning {
            background: #fff3e0;
            color: #f57c00;
            border-left: 4px solid #f57c00;
        }

        .results {
            display: none;
            padding: 40px;
            background: #f8f9ff;
        }

        .results.active {
            display: block;
        }

        .results-title {
            color: #667eea;
            font-size: 2em;
            margin-bottom: 30px;
            text-align: center;
        }

        .result-section {
            background: white;
            padding: 25px;
            border-radius: 12px;
            margin-bottom: 20px;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
        }

        .result-section h3 {
            color: #333;
            margin-bottom: 20px;
            padding-bottom: 10px;
            border-bottom: 2px solid #f0f0f0;
        }

        .result-item {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 12px 0;
            border-bottom: 1px solid #f0f0f0;
        }

        .result-item:last-child {
            border-bottom: none;
        }

        .result-label {
            color: #666;
            font-weight: 500;
        }

        .result-value {
            font-size: 1.1em;
            font-weight: 600;
            color: #333;
        }

        .result-total {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 20px;
            border-radius: 12px;
            text-align: center;
            margin-top: 30px;
        }

        .result-total h2 {
            font-size: 1.2em;
            margin-bottom: 10px;
            opacity: 0.9;
        }

        .result-total .amount {
            font-size: 2.5em;
            font-weight: bold;
        }

        .explanation {
            background: #fff3e0;
            padding: 20px;
            border-radius: 8px;
            margin-top: 20px;
        }

        .explanation h4 {
            color: #f57c00;
            margin-bottom: 10px;
        }

        .explanation ul {
            margin-left: 20px;
            color: #666;
            line-height: 1.8;
        }

        .hidden {
            display: none !important;
        }

        .tooltip {
            position: relative;
            display: inline-block;
            margin-left: 5px;
            cursor: help;
        }

        .tooltip-icon {
            background: #667eea;
            color: white;
            width: 20px;
            height: 20px;
            border-radius: 50%;
            display: inline-flex;
            align-items: center;
            justify-content: center;
            font-size: 12px;
            font-weight: bold;
        }

        .tooltip-content {
            visibility: hidden;
            width: 250px;
            background-color: #333;
            color: white;
            text-align: left;
            border-radius: 8px;
            padding: 10px;
            position: absolute;
            z-index: 1;
            bottom: 125%;
            left: 50%;
            margin-left: -125px;
            opacity: 0;
            transition: opacity 0.3s;
            font-size: 0.9em;
            line-height: 1.4;
        }

        .tooltip:hover .tooltip-content {
            visibility: visible;
            opacity: 1;
        }

        @media (max-width: 768px) {
            .form-container,
            .results {
                padding: 20px;
            }
            
            .button-group {
                flex-direction: column;
            }
            
            button {
                width: 100%;
            }
        }

        .special-case-alert {
            background: #e8f5e9;
            border-left: 4px solid #4caf50;
            color: #2e7d32;
            padding: 15px;
            border-radius: 8px;
            margin-bottom: 20px;
        }

        .error-message {
            color: #d32f2f;
            font-size: 0.9em;
            margin-top: 5px;
        }

        #printButton {
            background: #4caf50;
            color: white;
            margin-top: 20px;
        }

        #printButton:hover {
            background: #45a049;
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(76, 175, 80, 0.4);
        }

        @media print {
            body {
                background: white;
            }
            
            .container {
                box-shadow: none;
            }
            
            .button-group,
            #printButton {
                display: none;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="header">
            <h1>⚖️ Calculadora de Finiquito y Liquidación</h1>
            <p>Conforme a la Ley Federal del Trabajo - Actualizada 2025</p>
            <div class="progress-bar">
                <div class="progress-fill" id="progressBar"></div>
            </div>
        </div>

        <div class="form-container">
            <!-- Paso 1: Tipo de Trabajador -->
            <div class="step active" id="step1">
                <h2 class="step-title">Paso 1: Tipo de Trabajador</h2>
                <p class="step-description">Seleccione el tipo de trabajador para aplicar las reglas específicas de la LFT</p>
                
                <div class="form-group">
                    <label>Tipo de trabajador:</label>
                    <div class="radio-group">
                        <div class="radio-option">
                            <input type="radio" name="tipoTrabajador" value="general" id="general">
                            <label for="general">
                                <strong>Trabajador General</strong><br>
                                <small>Aplican las reglas generales de la LFT</small>
                            </label>
                        </div>
                        <div class="radio-option">
                            <input type="radio" name="tipoTrabajador" value="confianza" id="confianza">
                            <label for="confianza">
                                <strong>Trabajador de Confianza</strong><br>
                                <small>No hay reinstalación obligatoria (Art. 49-III)</small>
                            </label>
                        </div>
                        <div class="radio-option">
                            <input type="radio" name="tipoTrabajador" value="hogar" id="hogar">
                            <label for="hogar">
                                <strong>Trabajador del Hogar</strong><br>
                                <small>Reglas especiales Arts. 331-343</small>
                            </label>
                        </div>
                        <div class="radio-option">
                            <input type="radio" name="tipoTrabajador" value="campo" id="campo">
                            <label for="campo">
                                <strong>Trabajador del Campo</strong><br>
                                <small>Temporal o permanente (Arts. 279-284)</small>
                            </label>
                        </div>
                        <div class="radio-option">
                            <input type="radio" name="tipoTrabajador" value="plataformas" id="plataformas">
                            <label for="plataformas">
                                <strong>Trabajador de Plataformas Digitales</strong><br>
                                <small>Arts. 291-A a 291-U</small>
                            </label>
                        </div>
                        <div class="radio-option">
                            <input type="radio" name="tipoTrabajador" value="embarazada" id="embarazada">
                            <label for="embarazada">
                                <strong>Trabajadora Embarazada o en Lactancia</strong><br>
                                <small>Protección especial Art. 170</small>
                            </label>
                        </div>
                        <div class="radio-option">
                            <input type="radio" name="tipoTrabajador" value="menor" id="menor">
                            <label for="menor">
                                <strong>Trabajador Menor de Edad (15-18 años)</strong><br>
                                <small>Jornada reducida y vacaciones especiales</small>
                            </label>
                        </div>
                        <div class="radio-option">
                            <input type="radio" name="tipoTrabajador" value="aeronautico" id="aeronautico">
                            <label for="aeronautico">
                                <strong>Tripulante Aeronáutico</strong><br>
                                <small>30 días de vacaciones (Arts. 215-245)</small>
                            </label>
                        </div>
                        <div class="radio-option">
                            <input type="radio" name="tipoTrabajador" value="maritimo" id="maritimo">
                            <label for="maritimo">
                                <strong>Trabajador Marítimo</strong><br>
                                <small>Contratos por viaje (Arts. 187-214)</small>
                            </label>
                        </div>
                        <div class="radio-option">
                            <input type="radio" name="tipoTrabajador" value="otros" id="otros">
                            <label for="otros">
                                <strong>Otros Trabajadores Especiales</strong><br>
                                <small>Deportistas, ferrocarrileros, etc.</small>
                            </label>
                        </div>
                    </div>
                </div>

                <div class="button-group">
                    <button type="button" class="btn-primary" onclick="nextStep(1)">Continuar</button>
                </div>
            </div>

            <!-- Paso 2: Tipo de Terminación -->
            <div class="step" id="step2">
                <h2 class="step-title">Paso 2: Tipo de Terminación Laboral</h2>
                <p class="step-description">Indique la causa de terminación de la relación laboral</p>
                
                <div class="form-group">
                    <label>¿Cómo terminó la relación laboral?</label>
                    <div class="radio-group">
                        <div class="radio-option">
                            <input type="radio" name="tipoTerminacion" value="despidoInjustificado" id="despidoInjustificado">
                            <label for="despidoInjustificado">
                                <strong>Despido Injustificado</strong><br>
                                <small>Sin causa justificada o sin aviso por escrito (Art. 48-50)</small>
                            </label>
                        </div>
                        <div class="radio-option">
                            <input type="radio" name="tipoTerminacion" value="despidoJustificado" id="despidoJustificado">
                            <label for="despidoJustificado">
                                <strong>Despido Justificado</strong><br>
                                <small>Por causas del Art. 47 LFT</small>
                            </label>
                        </div>
                        <div class="radio-option">
                            <input type="radio" name="tipoTerminacion" value="rescisionTrabajador" id="rescisionTrabajador">
                            <label for="rescisionTrabajador">
                                <strong>Rescisión por el Trabajador (Causa Justificada)</strong><br>
                                <small>Por causas imputables al patrón (Art. 51)</small>
                            </label>
                        </div>
                        <div class="radio-option">
                            <input type="radio" name="tipoTerminacion" value="renuncia" id="renuncia">
                            <label for="renuncia">
                                <strong>Renuncia Voluntaria</strong><br>
                                <small>Por voluntad del trabajador</small>
                            </label>
                        </div>
                        <div class="radio-option">
                            <input type="radio" name="tipoTerminacion" value="terminacionContrato" id="terminacionContrato">
                            <label for="terminacionContrato">
                                <strong>Terminación de Contrato</strong><br>
                                <small>Por vencimiento, obra terminada, etc.</small>
                            </label>
                        </div>
                        <div class="radio-option">
                            <input type="radio" name="tipoTerminacion" value="terminacionColectiva" id="terminacionColectiva">
                            <label for="terminacionColectiva">
                                <strong>Terminación Colectiva</strong><br>
                                <small>Fuerza mayor, incosteabilidad, quiebra (Art. 434-436)</small>
                            </label>
                        </div>
                        <div class="radio-option">
                            <input type="radio" name="tipoTerminacion" value="muerte" id="muerte">
                            <label for="muerte">
                                <strong>Muerte del Trabajador</strong><br>
                                <small>Natural o por riesgo de trabajo</small>
                            </label>
                        </div>
                        <div class="radio-option">
                            <input type="radio" name="tipoTerminacion" value="incapacidad" id="incapacidad">
                            <label for="incapacidad">
                                <strong>Incapacidad Permanente</strong><br>
                                <small>Total o parcial</small>
                            </label>
                        </div>
                        <div class="radio-option">
                            <input type="radio" name="tipoTerminacion" value="negativa947" id="negativa947">
                            <label for="negativa947">
                                <strong>Negativa del Patrón al Juicio</strong><br>
                                <small>Art. 947 - Se niega a someterse o aceptar sentencia</small>
                            </label>
                        </div>
                    </div>
                </div>

                <div class="button-group">
                    <button type="button" class="btn-secondary" onclick="previousStep(2)">Anterior</button>
                    <button type="button" class="btn-primary" onclick="nextStep(2)">Continuar</button>
                </div>
            </div>

            <!-- Paso 3: Información Básica -->
            <div class="step" id="step3">
                <h2 class="step-title">Paso 3: Información Básica del Trabajador</h2>
                <p class="step-description">Ingrese los datos generales de la relación laboral</p>
                
                <div class="form-group">
                    <label>Fecha de Ingreso:
                        <span class="tooltip">
                            <span class="tooltip-icon">?</span>
                            <span class="tooltip-content">Fecha en que inició la relación laboral</span>
                        </span>
                    </label>
                    <input type="date" id="fechaIngreso" required>
                </div>

                <div class="form-group">
                    <label>Fecha de Terminación:
                        <span class="tooltip">
                            <span class="tooltip-icon">?</span>
                            <span class="tooltip-content">Fecha efectiva del despido o terminación</span>
                        </span>
                    </label>
                    <input type="date" id="fechaTerminacion" required>
                </div>

                <div class="form-group">
                    <label>Tipo de Contrato:</label>
                    <select id="tipoContrato">
                        <option value="indeterminado">Tiempo Indeterminado</option>
                        <option value="determinado">Tiempo Determinado</option>
                        <option value="obra">Por Obra Determinada</option>
                    </select>
                </div>

                <div class="form-group" id="duracionContratoGroup" style="display:none;">
                    <label>Duración del Contrato (en días):</label>
                    <input type="number" id="duracionContrato" min="1">
                </div>

                <div class="button-group">
                    <button type="button" class="btn-secondary" onclick="previousStep(3)">Anterior</button>
                    <button type="button" class="btn-primary" onclick="nextStep(3)">Continuar</button>
                </div>
            </div>

            <!-- Paso 4: Información Salarial -->
            <div class="step" id="step4">
                <h2 class="step-title">Paso 4: Información Salarial</h2>
                <p class="step-description">Ingrese los datos del salario y prestaciones</p>
                
                <div class="form-group">
                    <label>Salario Diario Integrado (SDI):
                        <span class="tooltip">
                            <span class="tooltip-icon">?</span>
                            <span class="tooltip-content">Incluye cuota diaria + prestaciones del Art. 84 LFT</span>
                        </span>
                    </label>
                    <input type="number" id="salarioDiario" step="0.01" min="0" required>
                </div>

                <div class="form-group">
                    <label>Salario Mínimo Vigente:
                        <span class="tooltip">
                            <span class="tooltip-icon">?</span>
                            <span class="tooltip-content">$248.93 para 2025 según ejemplo</span>
                        </span>
                    </label>
                    <input type="number" id="salarioMinimo" value="248.93" step="0.01" min="0" required>
                </div>

                <div class="form-group">
                    <label>¿El salario es variable?</label>
                    <div class="radio-group">
                        <div class="radio-option">
                            <input type="radio" name="salarioVariable" value="no" id="salarioFijo" checked>
                            <label for="salarioFijo">No, es fijo</label>
                        </div>
                        <div class="radio-option">
                            <input type="radio" name="salarioVariable" value="si" id="salarioVar">
                            <label for="salarioVar">Sí, es variable (comisiones, destajo, etc.)</label>
                        </div>
                    </div>
                </div>

                <div class="form-group" id="promedioSalarioGroup" style="display:none;">
                    <label>Promedio de los últimos 30 días trabajados:</label>
                    <input type="number" id="promedioSalario" step="0.01" min="0">
                </div>

                <div class="button-group">
                    <button type="button" class="btn-secondary" onclick="previousStep(4)">Anterior</button>
                    <button type="button" class="btn-primary" onclick="nextStep(4)">Continuar</button>
                </div>
            </div>

            <!-- Paso 5: Prestaciones y Condiciones Especiales -->
            <div class="step" id="step5">
                <h2 class="step-title">Paso 5: Prestaciones y Condiciones Especiales</h2>
                <p class="step-description">Indique las prestaciones contractuales y situaciones especiales</p>
                
                <div class="form-group">
                    <label>Días de Aguinaldo según contrato:
                        <span class="tooltip">
                            <span class="tooltip-icon">?</span>
                            <span class="tooltip-content">Mínimo legal: 15 días</span>
                        </span>
                    </label>
                    <input type="number" id="diasAguinaldo" value="15" min="15" required>
                </div>

                <div class="form-group">
                    <label>Porcentaje de Prima Vacacional:
                        <span class="tooltip">
                            <span class="tooltip-icon">?</span>
                            <span class="tooltip-content">Mínimo legal: 25%</span>
                        </span>
                    </label>
                    <input type="number" id="primaVacacional" value="25" min="25" step="1" required>
                </div>

                <div class="form-group">
                    <label>¿Aplica alguna de estas condiciones especiales?</label>
                    <div class="checkbox-group">
                        <div class="checkbox-option">
                            <input type="checkbox" id="riesgoTrabajo" value="riesgoTrabajo">
                            <label for="riesgoTrabajo">Es un riesgo de trabajo</label>
                        </div>
                        <div class="checkbox-option">
                            <input type="checkbox" id="sinAviso" value="sinAviso">
                            <label for="sinAviso">No recibió aviso por escrito del despido</label>
                        </div>
                        <div class="checkbox-option">
                            <input type="checkbox" id="juicioLargo" value="juicioLargo">
                            <label for="juicioLargo">El juicio excedió 12 meses</label>
                        </div>
                        <div class="checkbox-option">
                            <input type="checkbox" id="horasExtra" value="horasExtra">
                            <label for="horasExtra">Tiene horas extras no pagadas</label>
                        </div>
                    </div>
                </div>

                <div class="form-group" id="tipoRiesgoGroup" style="display:none;">
                    <label>Tipo de riesgo de trabajo:</label>
                    <select id="tipoRiesgo">
                        <option value="">Seleccione...</option>
                        <option value="temporal">Incapacidad Temporal</option>
                        <option value="parcial">Incapacidad Permanente Parcial</option>
                        <option value="total">Incapacidad Permanente Total</option>
                        <option value="muerte">Muerte por riesgo de trabajo</option>
                    </select>
                </div>

                <div class="button-group">
                    <button type="button" class="btn-secondary" onclick="previousStep(5)">Anterior</button>
                    <button type="button" class="btn-primary" onclick="nextStep(5)">Continuar</button>
                </div>
            </div>

            <!-- Paso 6: Información Adicional -->
            <div class="step" id="step6">
                <h2 class="step-title">Paso 6: Información Adicional</h2>
                <p class="step-description">Complete la información para el cálculo preciso</p>
                
                <div class="form-group">
                    <label>Días de vacaciones no disfrutadas:</label>
                    <input type="number" id="vacacionesPendientes" value="0" min="0">
                </div>

                <div class="form-group">
                    <label>Días trabajados en el año actual:
                        <span class="tooltip">
                            <span class="tooltip-icon">?</span>
                            <span class="tooltip-content">Para calcular proporcionales de aguinaldo y vacaciones</span>
                        </span>
                    </label>
                    <input type="number" id="diasTrabajadosAnio" min="0" max="365">
                </div>

                <div class="form-group" id="salariosVencidosGroup">
                    <label>Fecha de presentación de demanda (si aplica):
                        <span class="tooltip">
                            <span class="tooltip-icon">?</span>
                            <span class="tooltip-content">Para calcular salarios vencidos</span>
                        </span>
                    </label>
                    <input type="date" id="fechaDemanda">
                </div>

                <div class="form-group">
                    <label>¿Participó en reparto de utilidades (PTU)?</label>
                    <div class="radio-group">
                        <div class="radio-option">
                            <input type="radio" name="ptu" value="si" id="ptuSi">
                            <label for="ptuSi">Sí</label>
                        </div>
                        <div class="radio-option">
                            <input type="radio" name="ptu" value="no" id="ptuNo" checked>
                            <label for="ptuNo">No / No aplica</label>
                        </div>
                    </div>
                </div>

                <div class="alert alert-info">
                    <strong>📌 Nota importante:</strong> La PTU NO se computa como parte del salario para el cálculo de indemnizaciones según el Art. 129 LFT.
                </div>

                <div class="button-group">
                    <button type="button" class="btn-secondary" onclick="previousStep(6)">Anterior</button>
                    <button type="button" class="btn-primary" onclick="calcular()">Calcular Finiquito/Liquidación</button>
                </div>
            </div>
        </div>

        <!-- Sección de Resultados -->
        <div class="results" id="resultsSection">
            <h2 class="results-title">📊 Cálculo de Finiquito y Liquidación</h2>
            
            <div class="result-section">
                <h3>📋 Información General</h3>
                <div class="result-item">
                    <span class="result-label">Tipo de Trabajador:</span>
                    <span class="result-value" id="resTipoTrabajador"></span>
                </div>
                <div class="result-item">
                    <span class="result-label">Tipo de Terminación:</span>
                    <span class="result-value" id="resTipoTerminacion"></span>
                </div>
                <div class="result-item">
                    <span class="result-label">Antigüedad:</span>
                    <span class="result-value" id="resAntiguedad"></span>
                </div>
                <div class="result-item">
                    <span class="result-label">Salario Diario:</span>
                    <span class="result-value" id="resSalarioDiario"></span>
                </div>
            </div>

            <div class="result-section" id="indemnizacionSection">
                <h3>💰 Indemnización Constitucional</h3>
                <div class="result-item">
                    <span class="result-label">20 días por año de servicios:</span>
                    <span class="result-value" id="resIndemnizacion"></span>
                </div>
                <div class="result-item">
                    <span class="result-label">3 meses de salario adicionales:</span>
                    <span class="result-value" id="res3Meses"></span>
                </div>
            </div>

            <div class="result-section" id="salariosVencidosSection">
                <h3>⏱️ Salarios Vencidos</h3>
                <div class="result-item">
                    <span class="result-label">Días de salarios vencidos:</span>
                    <span class="result-value" id="resDiasVencidos"></span>
                </div>
                <div class="result-item">
                    <span class="result-label">Monto de salarios vencidos:</span>
                    <span class="result-value" id="resSalariosVencidos"></span>
                </div>
                <div class="result-item" id="interesesRow" style="display:none;">
                    <span class="result-label">Intereses (2% mensual):</span>
                    <span class="result-value" id="resIntereses"></span>
                </div>
            </div>

            <div class="result-section">
                <h3>🎁 Prestaciones Devengadas</h3>
                <div class="result-item">
                    <span class="result-label">Prima de Antigüedad:</span>
                    <span class="result-value" id="resPrimaAntiguedad"></span>
                </div>
                <div class="result-item">
                    <span class="result-label">Aguinaldo Proporcional:</span>
                    <span class="result-value" id="resAguinaldo"></span>
                </div>
                <div class="result-item">
                    <span class="result-label">Vacaciones Proporcionales:</span>
                    <span class="result-value" id="resVacaciones"></span>
                </div>
                <div class="result-item">
                    <span class="result-label">Prima Vacacional:</span>
                    <span class="result-value" id="resPrimaVacacional"></span>
                </div>
                <div class="result-item">
                    <span class="result-label">Vacaciones No Disfrutadas:</span>
                    <span class="result-value" id="resVacacionesPendientes"></span>
                </div>
            </div>

            <div class="result-section" id="casosEspecialesSection" style="display:none;">
                <h3>⚠️ Conceptos Especiales</h3>
                <div id="conceptosEspeciales"></div>
            </div>

            <div class="result-total">
                <h2>TOTAL A RECIBIR</h2>
                <div class="amount" id="totalAmount">$0.00</div>
            </div>

            <div class="explanation">
                <h4>📌 Base Legal del Cálculo:</h4>
                <ul id="baseLegal">
                </ul>
            </div>

            <div class="button-group">
                <button type="button" class="btn-secondary" onclick="reiniciar()">Nueva Consulta</button>
                <button type="button" id="printButton" onclick="window.print()">Imprimir Resultado</button>
            </div>
        </div>
    </div>

    <script>
        // Variables globales
        let currentStep = 1;
        const totalSteps = 6;
        let calculationData = {};

        // Listeners para cambios dinámicos
        document.addEventListener('DOMContentLoaded', function() {
            // Tipo de contrato
            document.getElementById('tipoContrato').addEventListener('change', function() {
                const duracionGroup = document.getElementById('duracionContratoGroup');
                if (this.value === 'determinado' || this.value === 'obra') {
                    duracionGroup.style.display = 'block';
                } else {
                    duracionGroup.style.display = 'none';
                }
            });

            // Salario variable
            document.querySelectorAll('input[name="salarioVariable"]').forEach(radio => {
                radio.addEventListener('change', function() {
                    const promedioGroup = document.getElementById('promedioSalarioGroup');
                    if (this.value === 'si') {
                        promedioGroup.style.display = 'block';
                    } else {
                        promedioGroup.style.display = 'none';
                    }
                });
            });

            // Riesgo de trabajo
            document.getElementById('riesgoTrabajo').addEventListener('change', function() {
                const tipoRiesgoGroup = document.getElementById('tipoRiesgoGroup');
                if (this.checked) {
                    tipoRiesgoGroup.style.display = 'block';
                } else {
                    tipoRiesgoGroup.style.display = 'none';
                }
            });

            // Actualizar clases selected en radio buttons
            document.querySelectorAll('.radio-option input').forEach(radio => {
                radio.addEventListener('change', function() {
                    // Remover selected de todos los del mismo grupo
                    document.querySelectorAll(`input[name="${this.name}"]`).forEach(r => {
                        r.closest('.radio-option').classList.remove('selected');
                    });
                    // Agregar selected al actual
                    if (this.checked) {
                        this.closest('.radio-option').classList.add('selected');
                    }
                });
            });
        });

        function updateProgressBar() {
            const progress = (currentStep / totalSteps) * 100;
            document.getElementById('progressBar').style.width = progress + '%';
        }

        function nextStep(step) {
            // Validar el paso actual
            if (!validateStep(step)) {
                return;
            }

            // Ocultar paso actual
            document.getElementById('step' + step).classList.remove('active');
            
            // Mostrar siguiente paso
            currentStep = step + 1;
            document.getElementById('step' + currentStep).classList.add('active');
            
            // Actualizar barra de progreso
            updateProgressBar();
            
            // Scroll al inicio
            window.scrollTo(0, 0);
        }

        function previousStep(step) {
            // Ocultar paso actual
            document.getElementById('step' + step).classList.remove('active');
            
            // Mostrar paso anterior
            currentStep = step - 1;
            document.getElementById('step' + currentStep).classList.add('active');
            
            // Actualizar barra de progreso
            updateProgressBar();
            
            // Scroll al inicio
            window.scrollTo(0, 0);
        }

        function validateStep(step) {
            let isValid = true;
            let errorMessage = '';

            switch(step) {
                case 1:
                    const tipoTrabajador = document.querySelector('input[name="tipoTrabajador"]:checked');
                    if (!tipoTrabajador) {
                        errorMessage = 'Por favor seleccione el tipo de trabajador';
                        isValid = false;
                    }
                    break;
                case 2:
                    const tipoTerminacion = document.querySelector('input[name="tipoTerminacion"]:checked');
                    if (!tipoTerminacion) {
                        errorMessage = 'Por favor seleccione el tipo de terminación';
                        isValid = false;
                    }
                    break;
                case 3:
                    const fechaIngreso = document.getElementById('fechaIngreso').value;
                    const fechaTerminacion = document.getElementById('fechaTerminacion').value;
                    if (!fechaIngreso || !fechaTerminacion) {
                        errorMessage = 'Por favor complete las fechas';
                        isValid = false;
                    } else if (new Date(fechaIngreso) >= new Date(fechaTerminacion)) {
                        errorMessage = 'La fecha de terminación debe ser posterior a la fecha de ingreso';
                        isValid = false;
                    }
                    break;
                case 4:
                    const salarioDiario = document.getElementById('salarioDiario').value;
                    if (!salarioDiario || salarioDiario <= 0) {
                        errorMessage = 'Por favor ingrese un salario válido';
                        isValid = false;
                    }
                    break;
            }

            if (!isValid) {
                alert(errorMessage);
            }

            return isValid;
        }

        function calcular() {
            // Recopilar todos los datos
            collectData();
            
            // Realizar cálculos
            const resultado = calcularFiniquito();
            
            // Mostrar resultados
            mostrarResultados(resultado);
            
            // Ocultar formulario y mostrar resultados
            document.querySelector('.form-container').style.display = 'none';
            document.getElementById('resultsSection').classList.add('active');
            
            // Scroll al inicio
            window.scrollTo(0, 0);
        }

        function collectData() {
            calculationData = {
                tipoTrabajador: document.querySelector('input[name="tipoTrabajador"]:checked')?.value,
                tipoTerminacion: document.querySelector('input[name="tipoTerminacion"]:checked')?.value,
                fechaIngreso: document.getElementById('fechaIngreso').value,
                fechaTerminacion: document.getElementById('fechaTerminacion').value,
                tipoContrato: document.getElementById('tipoContrato').value,
                duracionContrato: document.getElementById('duracionContrato').value,
                salarioDiario: parseFloat(document.getElementById('salarioDiario').value),
                salarioMinimo: parseFloat(document.getElementById('salarioMinimo').value),
                salarioVariable: document.querySelector('input[name="salarioVariable"]:checked')?.value === 'si',
                promedioSalario: parseFloat(document.getElementById('promedioSalario').value) || 0,
                diasAguinaldo: parseInt(document.getElementById('diasAguinaldo').value),
                primaVacacional: parseInt(document.getElementById('primaVacacional').value),
                riesgoTrabajo: document.getElementById('riesgoTrabajo').checked,
                tipoRiesgo: document.getElementById('tipoRiesgo').value,
                sinAviso: document.getElementById('sinAviso').checked,
                juicioLargo: document.getElementById('juicioLargo').checked,
                horasExtra: document.getElementById('horasExtra').checked,
                vacacionesPendientes: parseInt(document.getElementById('vacacionesPendientes').value) || 0,
                diasTrabajadosAnio: parseInt(document.getElementById('diasTrabajadosAnio').value) || 0,
                fechaDemanda: document.getElementById('fechaDemanda').value,
                participaPTU: document.querySelector('input[name="ptu"]:checked')?.value === 'si'
            };

            // Calcular antigüedad
            const fechaInicio = new Date(calculationData.fechaIngreso);
            const fechaFin = new Date(calculationData.fechaTerminacion);
            const diffTime = Math.abs(fechaFin - fechaInicio);
            calculationData.diasTotales = Math.ceil(diffTime / (1000 * 60 * 60 * 24));
            calculationData.aniosServicio = calculationData.diasTotales / 365;
            
            // Usar salario promedio si es variable
            if (calculationData.salarioVariable && calculationData.promedioSalario > 0) {
                calculationData.salarioCalculo = calculationData.promedioSalario;
            } else {
                calculationData.salarioCalculo = calculationData.salarioDiario;
            }
        }

        function calcularFiniquito() {
            const resultado = {
                indemnizacionConstitucional: 0,
                tresMeses: 0,
                salariosVencidos: 0,
                intereses: 0,
                primaAntiguedad: 0,
                aguinaldoProporcional: 0,
                vacacionesProporcionales: 0,
                primaVacacionalProporcional: 0,
                vacacionesNoDisfrutadas: 0,
                conceptosEspeciales: [],
                baseLegal: [],
                total: 0
            };

            const salario = calculationData.salarioCalculo;
            const anios = calculationData.aniosServicio;
            const diasTrabajadosAnio = calculationData.diasTrabajadosAnio;

            // INDEMNIZACIÓN SEGÚN TIPO DE TERMINACIÓN
            switch(calculationData.tipoTerminacion) {
                case 'despidoInjustificado':
                case 'rescisionTrabajador':
                    // Indemnización constitucional
                    if (calculationData.tipoContrato === 'indeterminado') {
                        resultado.indemnizacionConstitucional = salario * 20 * anios;
                        resultado.baseLegal.push('Art. 50 Fracción II: 20 días por año (tiempo indeterminado)');
                    } else if (calculationData.tipoContrato === 'determinado') {
                        if (anios < 1) {
                            resultado.indemnizacionConstitucional = salario * calculationData.diasTotales * 0.5;
                            resultado.baseLegal.push('Art. 50 Fracción I: 50% del tiempo servido (menor a 1 año)');
                        } else {
                            resultado.indemnizacionConstitucional = (salario * 180) + (salario * 20 * (anios - 1));
                            resultado.baseLegal.push('Art. 50 Fracción I: 6 meses primer año + 20 días por año siguiente');
                        }
                    }
                    
                    // 3 meses adicionales
                    resultado.tresMeses = salario * 90;
                    resultado.baseLegal.push('Art. 50 Fracción III: 3 meses de salario');
                    
                    // Salarios vencidos
                    if (calculationData.fechaDemanda) {
                        const fechaDemanda = new Date(calculationData.fechaDemanda);
                        const fechaTerminacion = new Date(calculationData.fechaTerminacion);
                        const diasVencidos = Math.ceil((fechaDemanda - fechaTerminacion) / (1000 * 60 * 60 * 24));
                        const diasMaximos = Math.min(diasVencidos, 365); // Máximo 12 meses
                        
                        resultado.salariosVencidos = salario * diasMaximos;
                        resultado.diasVencidos = diasMaximos;
                        resultado.baseLegal.push(`Art. 48: Salarios vencidos (máximo 12 meses) - ${diasMaximos} días`);
                        
                        // Intereses si excede 12 meses
                        if (calculationData.juicioLargo && diasVencidos > 365) {
                            const mesesExtra = Math.ceil((diasVencidos - 365) / 30);
                            resultado.intereses = resultado.salariosVencidos * 0.02 * mesesExtra;
                            resultado.baseLegal.push('Art. 48: Intereses 2% mensual capitalizable por exceder 12 meses');
                        }
                    }
                    break;
                    
                case 'despidoJustificado':
                    resultado.baseLegal.push('Art. 47: Despido justificado - Sin indemnización constitucional');
                    break;
                    
                case 'renuncia':
                    resultado.baseLegal.push('Renuncia voluntaria - Solo prestaciones devengadas');
                    break;
                    
                case 'terminacionColectiva':
                    resultado.tresMeses = salario * 90;
                    resultado.baseLegal.push('Art. 436: Terminación colectiva - 3 meses de salario');
                    break;
                    
                case 'muerte':
                    if (calculationData.riesgoTrabajo) {
                        resultado.conceptosEspeciales.push({
                            concepto: 'Indemnización por muerte (riesgo de trabajo)',
                            monto: salario * 5000
                        });
                        resultado.conceptosEspeciales.push({
                            concepto: 'Gastos funerarios',
                            monto: salario * 60
                        });
                        resultado.baseLegal.push('Art. 500-502: 5,000 días de salario + 2 meses gastos funerarios');
                    }
                    break;
                    
                case 'incapacidad':
                    if (calculationData.tipoRiesgo === 'total') {
                        resultado.conceptosEspeciales.push({
                            concepto: 'Incapacidad permanente total',
                            monto: salario * 1095
                        });
                        resultado.baseLegal.push('Art. 495: 1,095 días de salario por incapacidad total');
                    }
                    break;
                    
                case 'negativa947':
                    // Incluye todo del despido injustificado más sanciones
                    resultado.indemnizacionConstitucional = salario * 20 * anios;
                    resultado.tresMeses = salario * 90;
                    resultado.conceptosEspeciales.push({
                        concepto: '3 meses adicionales por negativa (Art. 947)',
                        monto: salario * 90
                    });
                    resultado.baseLegal.push('Art. 947: Negativa del patrón - Indemnización completa + 3 meses extra');
                    break;
            }

            // PRIMA DE ANTIGÜEDAD
            const salarioTopePrima = Math.min(salario, calculationData.salarioMinimo * 2);
            const aplicaPrimaAntiguedad = 
                calculationData.tipoTerminacion !== 'renuncia' || 
                (calculationData.tipoTerminacion === 'renuncia' && anios >= 15);
            
            if (aplicaPrimaAntiguedad) {
                resultado.primaAntiguedad = salarioTopePrima * 12 * anios;
                resultado.baseLegal.push(`Art. 162: Prima de antigüedad - 12 días por año (tope 2 salarios mínimos)`);
            }

            // AGUINALDO PROPORCIONAL
            resultado.aguinaldoProporcional = (salario * calculationData.diasAguinaldo) * (diasTrabajadosAnio / 365);
            resultado.baseLegal.push(`Art. 87: Aguinaldo proporcional - ${calculationData.diasAguinaldo} días`);

            // VACACIONES PROPORCIONALES
            const diasVacaciones = calcularDiasVacaciones(anios, calculationData.tipoTrabajador);
            resultado.vacacionesProporcionales = (salario * diasVacaciones) * (diasTrabajadosAnio / 365);
            resultado.baseLegal.push(`Art. 76: Vacaciones proporcionales - ${diasVacaciones} días`);

            // PRIMA VACACIONAL
            resultado.primaVacacionalProporcional = resultado.vacacionesProporcionales * (calculationData.primaVacacional / 100);
            resultado.baseLegal.push(`Art. 80: Prima vacacional ${calculationData.primaVacacional}%`);

            // VACACIONES NO DISFRUTADAS
            if (calculationData.vacacionesPendientes > 0) {
                resultado.vacacionesNoDisfrutadas = salario * calculationData.vacacionesPendientes;
                resultado.baseLegal.push(`Vacaciones no disfrutadas: ${calculationData.vacacionesPendientes} días`);
            }

            // CASOS ESPECIALES POR TIPO DE TRABAJADOR
            if (calculationData.tipoTrabajador === 'plataformas' && 
                (calculationData.tipoTerminacion === 'despidoInjustificado' || 
                 calculationData.tipoTerminacion === 'rescisionTrabajador')) {
                // Ajuste especial para plataformas digitales
                resultado.indemnizacionConstitucional = (salario * 90) + (salario * 20 * anios);
                resultado.baseLegal.push('Art. 291-Q: Plataformas digitales - 3 meses + 20 días por año');
            }

            // PRESUNCIONES ESPECIALES
            if (calculationData.sinAviso && calculationData.tipoTerminacion === 'despidoJustificado') {
                // Si no hubo aviso, se presume despido injustificado
                resultado.conceptosEspeciales.push({
                    concepto: 'Presunción de despido injustificado (sin aviso)',
                    monto: 0
                });
                resultado.baseLegal.push('Art. 47: Sin aviso por escrito = presunción de despido injustificado');
            }

            // Calcular total
            resultado.total = 
                resultado.indemnizacionConstitucional +
                resultado.tresMeses +
                resultado.salariosVencidos +
                resultado.intereses +
                resultado.primaAntiguedad +
                resultado.aguinaldoProporcional +
                resultado.vacacionesProporcionales +
                resultado.primaVacacionalProporcional +
                resultado.vacacionesNoDisfrutadas;

            // Agregar conceptos especiales al total
            resultado.conceptosEspeciales.forEach(concepto => {
                resultado.total += concepto.monto;
            });

            return resultado;
        }

        function calcularDiasVacaciones(anios, tipoTrabajador) {
            // Casos especiales
            if (tipoTrabajador === 'menor') {
                return 18; // Mínimo para menores
            }
            if (tipoTrabajador === 'aeronautico') {
                return Math.min(30 + Math.floor(anios), 60); // 30 días + 1 por año hasta 60
            }
            if (tipoTrabajador === 'maritimo') {
                let dias = 12;
                if (anios >= 1) dias = 14;
                if (anios >= 2) dias = 16;
                if (anios >= 3) dias = 18;
                if (anios >= 4) dias = 20;
                if (anios >= 5) dias = 22;
                if (anios >= 10) dias = 24;
                return dias;
            }

            // Caso general
            if (anios < 1) return 12;
            if (anios < 2) return 14;
            if (anios < 3) return 16;
            if (anios < 4) return 18;
            if (anios < 5) return 20;
            
            // A partir del 6° año, +2 días cada 5 años
            const aniosExtra = Math.floor((anios - 5) / 5);
            return Math.min(20 + (aniosExtra * 2), 30);
        }

        function formatCurrency(amount) {
            return new Intl.NumberFormat('es-MX', {
                style: 'currency',
                currency: 'MXN'
            }).format(amount);
        }

        function formatearTipoTrabajador(tipo) {
            const tipos = {
                'general': 'Trabajador General',
                'confianza': 'Trabajador de Confianza',
                'hogar': 'Trabajador del Hogar',
                'campo': 'Trabajador del Campo',
                'plataformas': 'Trabajador de Plataformas Digitales',
                'embarazada': 'Trabajadora Embarazada/Lactancia',
                'menor': 'Trabajador Menor de Edad',
                'aeronautico': 'Tripulante Aeronáutico',
                'maritimo': 'Trabajador Marítimo',
                'otros': 'Otros Trabajadores Especiales'
            };
            return tipos[tipo] || tipo;
        }

        function formatearTipoTerminacion(tipo) {
            const tipos = {
                'despidoInjustificado': 'Despido Injustificado',
                'despidoJustificado': 'Despido Justificado',
                'rescisionTrabajador': 'Rescisión por el Trabajador (Causa Justificada)',
                'renuncia': 'Renuncia Voluntaria',
                'terminacionContrato': 'Terminación de Contrato',
                'terminacionColectiva': 'Terminación Colectiva',
                'muerte': 'Muerte del Trabajador',
                'incapacidad': 'Incapacidad Permanente',
                'negativa947': 'Negativa del Patrón al Juicio (Art. 947)'
            };
            return tipos[tipo] || tipo;
        }

        function mostrarResultados(resultado) {
            // Información general
            document.getElementById('resTipoTrabajador').textContent = formatearTipoTrabajador(calculationData.tipoTrabajador);
            document.getElementById('resTipoTerminacion').textContent = formatearTipoTerminacion(calculationData.tipoTerminacion);
            
            const anios = Math.floor(calculationData.aniosServicio);
            const meses = Math.floor((calculationData.aniosServicio - anios) * 12);
            document.getElementById('resAntiguedad').textContent = `${anios} años, ${meses} meses`;
            
            document.getElementById('resSalarioDiario').textContent = formatCurrency(calculationData.salarioCalculo);

            // Indemnización
            const indemnizacionSection = document.getElementById('indemnizacionSection');
            if (resultado.indemnizacionConstitucional > 0 || resultado.tresMeses > 0) {
                indemnizacionSection.style.display = 'block';
                document.getElementById('resIndemnizacion').textContent = formatCurrency(resultado.indemnizacionConstitucional);
                document.getElementById('res3Meses').textContent = formatCurrency(resultado.tresMeses);
            } else {
                indemnizacionSection.style.display = 'none';
            }

            // Salarios vencidos
            const salariosVencidosSection = document.getElementById('salariosVencidosSection');
            if (resultado.salariosVencidos > 0) {
                salariosVencidosSection.style.display = 'block';
                document.getElementById('resDiasVencidos').textContent = resultado.diasVencidos || '0';
                document.getElementById('resSalariosVencidos').textContent = formatCurrency(resultado.salariosVencidos);
                
                if (resultado.intereses > 0) {
                    document.getElementById('interesesRow').style.display = 'flex';
                    document.getElementById('resIntereses').textContent = formatCurrency(resultado.intereses);
                }
            } else {
                salariosVencidosSection.style.display = 'none';
            }

            // Prestaciones
            document.getElementById('resPrimaAntiguedad').textContent = formatCurrency(resultado.primaAntiguedad);
            document.getElementById('resAguinaldo').textContent = formatCurrency(resultado.aguinaldoProporcional);
            document.getElementById('resVacaciones').textContent = formatCurrency(resultado.vacacionesProporcionales);
            document.getElementById('resPrimaVacacional').textContent = formatCurrency(resultado.primaVacacionalProporcional);
            document.getElementById('resVacacionesPendientes').textContent = formatCurrency(resultado.vacacionesNoDisfrutadas);

            // Casos especiales
            if (resultado.conceptosEspeciales.length > 0) {
                const casosEspecialesSection = document.getElementById('casosEspecialesSection');
                casosEspecialesSection.style.display = 'block';
                const conceptosDiv = document.getElementById('conceptosEspeciales');
                conceptosDiv.innerHTML = '';
                
                resultado.conceptosEspeciales.forEach(concepto => {
                    const div = document.createElement('div');
                    div.className = 'result-item';
                    div.innerHTML = `
                        <span class="result-label">${concepto.concepto}:</span>
                        <span class="result-value">${formatCurrency(concepto.monto)}</span>
                    `;
                    conceptosDiv.appendChild(div);
                });
            }

            // Total
            document.getElementById('totalAmount').textContent = formatCurrency(resultado.total);

            // Base legal
            const baseLegalList = document.getElementById('baseLegal');
            baseLegalList.innerHTML = '';
            resultado.baseLegal.forEach(item => {
                const li = document.createElement('li');
                li.textContent = item;
                baseLegalList.appendChild(li);
            });
        }

        function reiniciar() {
            // Reiniciar formulario
            document.querySelectorAll('input[type="radio"]').forEach(radio => {
                radio.checked = false;
                radio.closest('.radio-option')?.classList.remove('selected');
            });
            document.querySelectorAll('input[type="checkbox"]').forEach(checkbox => {
                checkbox.checked = false;
            });
            document.querySelectorAll('input[type="text"], input[type="number"], input[type="date"]').forEach(input => {
                if (input.id !== 'salarioMinimo' && input.id !== 'diasAguinaldo' && input.id !== 'primaVacacional') {
                    input.value = '';
                }
            });

            // Reiniciar valores por defecto
            document.getElementById('salarioMinimo').value = '248.93';
            document.getElementById('diasAguinaldo').value = '15';
            document.getElementById('primaVacacional').value = '25';
            document.getElementById('vacacionesPendientes').value = '0';

            // Reiniciar navegación
            currentStep = 1;
            document.querySelectorAll('.step').forEach(step => {
                step.classList.remove('active');
            });
            document.getElementById('step1').classList.add('active');
            
            // Mostrar formulario y ocultar resultados
            document.querySelector('.form-container').style.display = 'block';
            document.getElementById('resultsSection').classList.remove('active');
            
            // Reiniciar barra de progreso
            updateProgressBar();
            
            // Scroll al inicio
            window.scrollTo(0, 0);
        }
    </script>
</body>
</html>
